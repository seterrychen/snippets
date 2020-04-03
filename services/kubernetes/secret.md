## Usage
### Create from file
```
kubectl create secret generic db-user-pass --from-file=./username.txt --from-file=./password.txt
```

pod.yml
```
    spec:
      containers:
        - name: xxxx
          image: xxxx
          volumeMounts:
          - name: db-secret
            mountPath: /etc/secret-keys
            readOnly: true
      volumes:
        - name: db-secret
          secret:
            secretName: db-user-pass
```
