# MongoDb

```yaml
version: '3'
services:
  yh-mongodb:
    image: "bitnami/mongodb:latest"
    volumes:
      - "yh-mongodb-data:/bitnami/mongodb"
    ports:
      - "27017:27017"
    environment:
      MONGODB_PORT_NUMBER: "27017"
      MONGODB_ROOT_USER: "root"
      MONGODB_ROOT_PASSWORD: "123456"
      MONGODB_USERNAME: "yhuser"
      MONGODB_PASSWORD: "123456"
      MONGODB_DATABASE: "demo"

volumes:
  yh-mongodb-data: {}
      

```

