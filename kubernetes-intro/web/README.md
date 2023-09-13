Для выполнения задания пришлось создать файл homework.html который будет копироваться в контейнер в созданную
директорию /app.

Слхдаем манифест web-pod.yaml в котором учитывем все из задания и 
описываем каким образом необходимо запустить контейнер с нашим Image 

Билдим контейнер и пушим его в DockerHub
docker build -t alexgavaz/web:v1 ./kubernetes-intro/web
docker push alexgavaz/web:v1

Запускаем контейнер
kubectl apply -f ./kubernetes-intro/web-pod.yaml 

Открываем порт 8000
kubectl port-forward --address 0.0.0.0 pod/web 8000:8000

должны работать ссылки
http://localhost:8000/homework.html
http://localhost:8000/index.html