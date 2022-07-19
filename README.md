# Kubernetes-KEDA-AppInsights-Kafka-EventHubs-DotNet6_ContagemAcessos

 Objetos para Deployment de um Worker Service (contagem de acessos) no Kubernetes utilizando KEDA, Helm, monitoramento com Azure Application Insights, Apache Kafka (a partir de uma instância do Azure Event Hubs) e .NET 6.

Worker Service para consumo de **mensagens vinculadas a um tópico do Apache Kafka** (imagem **renatogroffe/workercontagem-appinsights-kafka-dotnet6**) - é justamente esta aplicação que será escalada via **KEDA**:

**https://github.com/renatogroffe/DotNet6-WorkerService-AppInsights-Kafka-Partitions-SqlServer_ContagemAcessos**

Projeto que serviu de base para o **envio de mensagens a um tópico do Apache Kafka** (imagem **renatogroffe/apicontagem-appinsights-kafka-dotnet6**):

**https://github.com/renatogroffe/ASPNETCore6-REST_API-AppInsights-Kafka-Partitions_ContagemAcessos**

No arquivo **keda-instalacao&sdot;sh** estão as instruções para instalação do KEDA **(Kubernetes Event-driven Autoscaling)** em um **cluster Kubernetes**.

Para os testes de carga que escalam a aplicação utilizei o pacote npm [**loadtest**](https://www.npmjs.com/package/loadtest). O exemplo a seguir procederá com o envio de **5 mil requisições**, simulando **70 usuários concorrentes**:

**loadtest -c 70 -n 5000 -k** ***ENDPOINT***