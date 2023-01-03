
1. Install, create image, push to dockerhub

    cd comments
     ```
    npm install
    docker build -t turepository/comments .
    docker push turepository/comments ```

    cd event-bus
     ```
    npm install
    docker build -t turepository/event-bus .
    docker push turepository/event-bus ```

    cd moderation
     ```
    npm install
    docker build -t turepository/moderation .
    docker push turepository/ ```

    cd query
     ```
    npm install
    docker build -t turepository/query .
    docker push turepository/query ```

    cd posts
     ```
    npm install
    docker build -t turepository/posts .
    docker push turepository/posts ```

    cd client
     ```
    npm install
    docker build -t turepository/client .
    docker push turepository/client ```
 
2. Create services and deployments kubernetes

    cd infra/k8s
     ```
    kubectl apply -f comments-depl.yaml   
    kubectl apply -f event-bus-depl.yaml  
    kubectl apply -f moderation-depl.yaml   
    kubectl apply -f query-depl.yaml 
    kubectl apply -f posts-depl.yaml   
    kubectl apply -f client-depl.yaml  

    kubectl apply -f posts-srv.yaml  

    kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.5.1/deploy/static/provider/cloud/deploy.yaml

    kubectl apply -f ingress-srv.yaml 
 ```

3. Run with Skaffold
    You must have skaffold installed
    ```
    skaffold dev
    ```





