## Install on K8s
### StatefulSet
```
kind: StatefulSet
apiVersion: apps/v1
metadata:
  name: traefik
  labels:
    app: traefik

spec:
  replicas: 1
  selector:
    matchLabels:
      app: traefik
  serviceName: traefik
  template:
    metadata:
      labels:
        app: traefik
    spec:
      serviceAccountName: traefik-ingress-controller
      nodeSelector:
        nodeType: general
      containers:
        - name: traefik
          image: traefik:v2.0
          args:
          - --api.insecure
          - --accesslog
          - --entrypoints.web.Address=:80
          - --entrypoints.websecure.Address=:443
          - --providers.kubernetescrd
          - --certificatesresolvers.default.acme.tlschallenge
          - --certificatesresolvers.default.acme.email=email@xxx.com
          - --certificatesresolvers.default.acme.storage=/letsencrypt/acme.json
          volumeMounts:
          - name: traefik-storage
            mountPath: /letsencrypt
          ports:
          - name: web
            containerPort: 80
          - name: websecure
            containerPort: 443
          - name: admin
            containerPort: 8080
  volumeClaimTemplates:
  - metadata:
      name: traefik-storage
    spec:
      accessModes:
      - ReadWriteOnce
      storageClassName: gp2
      resources:
        requests:
          storage: 2Gi
```

### Service Account
```
apiVersion: v1
kind: ServiceAccount
metadata:
  name: traefik-ingress-controller
```

### Service
````
apiVersion: v1
kind: Service
metadata:
  name: traefik
  # To enable proxy protocol to forward client info
  #annotations:
  #  service.beta.kubernetes.io/aws-load-balancer-proxy-protocol: "*"

spec:
  type: LoadBalancer
  ports:
    - protocol: TCP
      name: web
      port: 80
    - protocol: TCP
      name: websecure
      port: 443
  selector:
    app: traefik
---
apiVersion: v1
kind: Service
metadata:
  name: traefik-ui

spec:
  ports:
    - protocol: TCP
      name: admin
      port: 8080
  selector:
    app: traefik
```

### Traefik K8s objects
```
apiVersion: apiextensions.k8s.io/v1beta1
kind: CustomResourceDefinition
metadata:
  name: ingressroutes.traefik.containo.us

spec:
  group: traefik.containo.us
  version: v1alpha1
  names:
    kind: IngressRoute
    plural: ingressroutes
    singular: ingressroute
  scope: Namespaced

---
apiVersion: apiextensions.k8s.io/v1beta1
kind: CustomResourceDefinition
metadata:
  name: ingressroutetcps.traefik.containo.us

spec:
  group: traefik.containo.us
  version: v1alpha1
  names:
    kind: IngressRouteTCP
    plural: ingressroutetcps
    singular: ingressroutetcp
  scope: Namespaced

---
apiVersion: apiextensions.k8s.io/v1beta1
kind: CustomResourceDefinition
metadata:
  name: middlewares.traefik.containo.us

spec:
  group: traefik.containo.us
  version: v1alpha1
  names:
    kind: Middleware
    plural: middlewares
    singular: middleware
  scope: Namespaced

---
apiVersion: apiextensions.k8s.io/v1beta1
kind: CustomResourceDefinition
metadata:
  name: tlsoptions.traefik.containo.us

spec:
  group: traefik.containo.us
  version: v1alpha1
  names:
    kind: TLSOption
    plural: tlsoptions
    singular: tlsoption
  scope: Namespaced

---
kind: ClusterRole
apiVersion: rbac.authorization.k8s.io/v1beta1
metadata:
  name: traefik-ingress-controller

rules:
  - apiGroups:
      - ""
    resources:
      - services
      - endpoints
      - secrets
    verbs:
      - get
      - list
      - watch
  - apiGroups:
      - extensions
    resources:
      - ingresses
    verbs:
      - get
      - list
      - watch
  - apiGroups:
      - extensions
    resources:
      - ingresses/status
    verbs:
      - update
  - apiGroups:
      - traefik.containo.us
    resources:
      - middlewares
    verbs:
      - get
      - list
      - watch
  - apiGroups:
      - traefik.containo.us
    resources:
      - ingressroutes
    verbs:
      - get
      - list
      - watch
  - apiGroups:
      - traefik.containo.us
    resources:
      - ingressroutetcps
    verbs:
      - get
      - list
      - watch
  - apiGroups:
      - traefik.containo.us
    resources:
      - tlsoptions
    verbs:
      - get
      - list
      - watch

---
kind: ClusterRoleBinding
apiVersion: rbac.authorization.k8s.io/v1beta1
metadata:
  name: traefik-ingress-controller

roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: traefik-ingress-controller
subjects:
  - kind: ServiceAccount
    name: traefik-ingress-controller
```
