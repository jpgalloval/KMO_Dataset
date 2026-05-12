# Instruções para a utilização deste template.

**Antes do commit inicial, remova este arquivo.**

Este repositório fornece a estrutura e os arquivos necessários de um projeto específico. Um projeto deve ter objetivos e um fim. Uma boa métrica é condicionar cada *projeto* a um artigo científico produzido. 

A organização das pastas proposta segue as melhores práticas para facilitar a colaboração e a reprodutibilidade da pesquisa, e deve ser seguida o máximo que for possível, para garantir a organização entre os membros do laboratório.

## Configuração inicial do template

Após clonar o repositório, você terá este arquivo e todas as pastas devidamente criadas, mas precisará configurar o ambiente Anaconda. O Anaconda é uma plataforma que facilita o gerenciamento de pacotes e ambientes para Python.

Um ambiente do Conda, também conhecido como "conda environment", é um diretório isolado que contém uma coleção específica de pacotes que são necessários para seu projeto. Cada ambiente pode ter diferentes versões de pacotes, incluindo do Python, permitindo que você crie condições específicas para diferentes projetos sem que os pacotes interfiram uns com os outros. Isso é especialmente útil quando diferentes projetos requerem diferentes versões de pacotes ou do Python. Ao usar ambientes, você pode alternar entre essas condições específicas conforme necessário.

Primeiro, verifique se o Anaconda está instalado corretamente. Abra o terminal e digite:

```shell
conda --version
```

Se o Anaconda estiver instalado corretamente, você verá a versão do conda exibida. Se não, você precisará [instalar o miniconda](https://docs.anaconda.com/free/anaconda/install/index.html).

Depois de confirmar que o Anaconda está instalado, você precisará criar um novo ambiente conda para este projeto. 

### Opção 1: Criando um novo ambiente
Isso pode ser feito com o seguinte comando:

```shell
conda create --name myenv
```

Substitua `myenv` pelo nome que você deseja dar ao seu ambiente.

Para ativar o ambiente, use o comando:

```shell
conda activate myenv
```

Agora que você tem um ambiente conda configurado, você pode instalar as dependências necessárias para este projeto.

Para instalar pacotes para um projeto Python, você pode usar o comando `conda install`. Por exemplo, para instalar os pacotes `numpy`, `pandas` e `matplotlib` no Python 3.10, você pode usar o seguinte comando:

```shell
conda install python=3.10 numpy pandas matplotlib
```

Se você já tiver instalado o Python no ambiente, pode usar o `pip` também. Sempre que possível, dê preferência aos pacotes do conda:

```shell
pip install numpy pandas matplotlib
```

Depois de instalar todos os pacotes necessários, você pode salvar as informações do seu ambiente em um arquivo `environment.yml` usando o comando `conda env export`. Isso cria um arquivo que lista todos os pacotes instalados no seu ambiente, permitindo que você recrie facilmente o ambiente em outro lugar. Aqui está o comando:

```shell
conda env export > environment.yml
```

Este comando cria um arquivo `environment.yml` no diretório atual com todas as informações do seu ambiente. Crie-o na raiz do projeto.

O arquivo `environment.yml` é crucial para garantir a reprodutibilidade do seu projeto. Ele lista todas as dependências do seu projeto, incluindo as versões específicas que você usou. Isso significa que qualquer pessoa (incluindo você, no futuro) pode recriar o ambiente exato que você usou para executar seu projeto. Isso é especialmente importante em projetos de ciência de dados, onde pequenas diferenças nas versões dos pacotes podem levar a resultados diferentes. Manter o `environment.yml` atualizado no controle de versão garante que todas as mudanças nas dependências do projeto sejam rastreadas. Você deve gerar novamente o `environment.yml` sempre que adicionar, atualizar ou remover dependências do seu projeto, isto é, sempre que usar `conda install` ou `pip install`.

### Opção 2: utilizando o environment.yml existente

Em vez de criar um novo ambiente e instalar as dependências manualmente, você pode alterar o arquivo `environment.yml` e incluir nele o nome do ambiente e as dependências (conda ou pip) necessárias. Depois, use o comando a seguir para criá-lo:

```shell
conda env create -f environment.yml
conda activate myenv
```

Substitua `myenv` pelo nome do ambiente que você definiu no arquivo `environment.yml`.

## Arquivos .gitkeep

Os arquivos `.gitkeep` estão presentes na árvore do projeto para garantir que o Git não ignore as pastas vazias no template. O Git normalmente ignora as pastas vazias durante o controle de versão, o que resultaria num template vazio. Ao incluir um arquivo `.gitkeep` em uma pasta vazia, você está informando ao Git que essa pasta deve ser rastreada e incluída no controle de versão, mesmo que não haja arquivos dentro dela no momento. Uma vez que você inclua algum arquivo na pasta, você pode remover o arquivo `.gitkeep` e a pasta será rastreada normalmente pelo Git.

## Instruções adicionais

Leia o [README.md](/).