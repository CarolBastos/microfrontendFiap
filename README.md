# 🚀 Microfrontends com Angular e Module Federation  

Este repositório contém um exemplo de arquitetura **microfrontend** em Angular, utilizando **Webpack Module Federation** para dividir a aplicação em múltiplos módulos independentes.  

## 📌 **Comandos Principais**  

### **Criar o projeto principal (Shell/Host)**  
```sh
ng new microfrontendFiap --create-application="false"
```
🔹 **O que esse comando faz?**  
- Cria um novo workspace Angular chamado `microfrontendFiap`.  
- O argumento `--create-application="false"` impede a criação automática de uma aplicação dentro do workspace, permitindo que sub-aplicações sejam adicionadas manualmente.  

---

### **Criar um Microfrontend (Remote)**  
```sh
ng g application microfrontend-app --routing --no-standalone
```
🔹 **O que esse comando faz?**  
- Gera uma nova aplicação Angular dentro do workspace.  
- O argumento `--routing` adiciona suporte a roteamento no microfrontend.  
- O argumento `--no-standalone` cria a aplicação no formato tradicional baseado em `NgModule`, em vez da nova API de componentes standalone do Angular 15+.  

---

### **Adicionar suporte a Module Federation**  
Execute o seguinte comando dentro do workspace para instalar **Module Federation**:  
```sh
ng add @angular-architects/module-federation --project microfront-app --port 4300
```
Escolha se a aplicação será **Host (shell)** ou **Remote (microfrontend)** quando solicitado.  

## 🚀 **Como Rodar o Projeto?**  

Inicie primeiramente o  **shell (host)**:  
```sh
ng serve host-app -o
```

Inicie o **microfrontend-app**:  
```sh
ng serve microfrontend-app -o
```

Agora, o **shell (host)** pode carregar dinamicamente o **microfrontend** via Webpack Module Federation.  

---

## 📚 **Mais Informações**  
Se precisar de mais detalhes sobre a configuração e comunicação entre os microfrontends, consulte a [documentação oficial](https://angular.io/).  

Se tiver dúvidas ou quiser melhorias no projeto, sinta-se à vontade para contribuir! 🚀💡  

