## 🙌 Node App & Mongodb Docker

Node 백앤드 , React 프론트 , Mongodb 서비스를 도커화시켜 컨테이너간의 통신을 적용한 프로젝트입니다.


-  도커 설치필요

## 🛠DB통신 네트워크 생성

```
docker network create goals-net
```

## 🛠Mongodb 설정
- Mongodb 컨테이너 실행
```
docker run --rm -d -p 27017:27017 -v data:/data/db   
 -e MONGO_INITDB_ROOT_USERNAME=root
 -e MONGO_INITDB_ROOT_PASSWORD=secret
 --network 	   
 --name mongodb mongo
```

## 🛠React 설정
- React 이미지 빌드

```
cd frontend
docker build -t goals-react .
```

- React 컨테이너 실행

```
docker run --name golas-react-app -it --rm
-v "D:/dev/docker_leaner/docker_app/frontend/src:/app/src"
-p 3000:3000 golas-react
```

## 🛠Node 설정
- Node 이미지 빌드

```
cd backend
docker build -t goals-node .
```
- Node 컨테이너 실행

```
docker run --rm -d -p 80:80  
 -v 경로\backend\:/app
 -v logs:/app/logs   
 -v /app/node_modules  
 --network goals-net
 --name goals-node-app goals-node
```


##  📢 참조
- <u>https://www.udemy.com/course/docker-kubernetes-2022/</u>
</u>
