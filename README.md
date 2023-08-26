# Criação de Cluster Local Kubernetes com Kind
Se você está buscando criar um cluster Kubernetes para fins de teste sem a necessidade de implantá-lo em um serviço em nuvem ou máquina dedicada, o create-cluster-local-kubernetes é a solução ideal. Este repositório oferece um script para criar um cluster Kubernetes local usando o Kind (Kubernetes in Docker) junto com extensões essenciais para facilitar os testes.

## 📌 Por que usar o Kind?
O Kind é uma ferramenta poderosa que simplifica a criação de clusters Kubernetes ao executar cada nó do cluster como um container Docker. Isso oferece uma abstração valiosa para desenvolvimento e teste local.

## 🔎 Extensões para Facilitar os Testes
Ao criar um cluster com o Kind, você tem a flexibilidade de adicionar extensões importantes que simulam ambientes mais complexos. Neste repositório, já incluímos por padrão duas extensões populares:

**1. Ingress Controller:** O script irá automaticamente configurar o Ingress, atuando como um proxy para permitir o acesso externo aos serviços dentro do cluster.

**2. MetalLB:** O MetalLB é uma ferramenta útil, especialmente para cenários on-premise, que oferece a funcionalidade de balanceamento de carga, permitindo a criação de balanceadores de carga dentro do cluster.

Claro, você também pode personalizar a configuração de acordo com suas necessidades.

## 📁 Estrutura do Repositório
```
create-cluster-local-kubernetes/
├── config/
│   ├── config.yaml
│   ├── metallb/
│   │   └── metallb.yaml
│   └── nginx/
│       └── ingress.yaml
├── libs/
│   ├── functions_deps.sh
│   └── functions_main.sh
└── create-cluster-local.sh
```
- config/: Contém os arquivos de configuração para instalação do Ingress e do MetalLB.
- libs/: Fornece scripts com funções auxiliares usadas no script principal.
- create-cluster-local.sh: O script principal que concentra todo o processo de criação do cluster. Ele oferece a flexibilidade de adicionar ou remover extensões de acordo com as suas preferências.

## 💻 VM de Teste
No diretório também existe um arquivo chamado Vagrantfile, ele serve para subi uma vm de teste usando o Fedora 37 no VirtualBox.
- Para subir a vm basta rodar o comando: ```vagrant up```.
- Depois que subir só precisa acessar a vm via ssh utilizando o comando: ```vagrant ssh```.

## 🤝 Colaborador

Script criado por:

<table>
  <tr>
    <td align="center">
      <a href="#">
        <img src="https://avatars.githubusercontent.com/u/77215294?v=4" width="100px;"alt="Foto de Erik Nathan no GitHub"/><br>
        <sub>
          <b>Erik Nathan</b>
        </sub>
      </a>
    </td>
  </tr>
</table>

## 📝 Licença

Esse projeto está sob licença. Veja o arquivo [LICENÇA](LICENSE.md) para mais detalhes.
