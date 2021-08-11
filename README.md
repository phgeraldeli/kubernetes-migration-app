# kubernetes-migration-app
Aplication created in docker/kubernetes course. This Repository documents the proccess to migrate from docker to kubernetes.


Os arquivos criados para uso no kubernetes são descritos em k8s/*

Para aplicar esses arquivos basta rodar: *kubectl apply -f k8s*


## Passos

* O primeiro passo foi excluir toda a configuração que tinhamos para utilizar docker-compose. *(commit ace1a0947a3937e1496967742ff2148f6db8170d)*
* Em seguida foi criado os arquivos de deployment e service do worker e client. *(commit faa67615163f72993e9f9449fe47c89562af3d85 / e51e1be856faf8a792e47b9432698cdcc1cd02e8)*
* Logo após foi criado os arquivos de deployment e service de todos os componentes das aplicações.
* Para o banco de dados foi criado uma secret executando o comando *kubectl create secret generic pgpassword --from-literal PGPASSWORD=password123* e foi associado essa secret dentro do configmap e deployment da aplicação.
* Por fim, foi criado um ingress com regras de / para o client e /api com reescrita para / para o server.
