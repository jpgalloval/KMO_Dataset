# (Repositório Base)

(Descrição do projeto.)

## Estrutura de pastas

As pastas são estruturadas assim:
```plain
.
├── code/
├── data/
│   ├── clean/
│   └── raw/
├── doc/
│   ├── meetings/
│   ├── notes/
│   ├── reports/
│   └── resources/
├── include/
├── results/
│   ├── figures/
│   └── pictures/
├── temp/
│   ├── cache/
│   ├── debug/
│   ├── log/
│   └── visualization/
├── .gitignore
├── environment.yml
├── LICENSE
└── README.md
```

Em que:

- `code/`: Contém o código fonte do projeto, organizado em subpastas por funcionalidade.
- `data/`: Armazena os dados utilizados pelo projeto, divididos em dados brutos (`raw`) e limpos (`clean`). NÃO DEVE SER EDITADO NUNCA.
- `doc/`: Documentação do projeto, incluindo atas de reuniões (`meetings/`), notas de pesquisa (`notes/`), relatórios e o texto final da pesquisa (`reports/`) e bibliografia de referência ou recursos adicionais de terceiros (`resources/`).
- `include/`: Código de terceiros para ser incluído no projeto.
- `results/`: Armazena os resultados do projeto, como gráficos (`figures`) e imagens gerais (`pictures`) que não sejam gráficos, como diagramas, etc.
- `temp/`: Arquivos temporários gerados durante a execução do projeto. Este é o local inicial para criar arquivos que servirão apenas de teste rápido. Também é onde seu programa deve salvar arquivos destinados à visualização do código (`visualization`), arquivos de depuração (`debug`), logs para serem analisados (`log`) e também possíveis arquivos de `cache`, como, por exemplo, modelos treinados.
- `.gitignore`: arquivo que configura as extensões de arquivos que serão ignoradas pelo [Git](https://git-scm.com/), sistema de versão de códigos que você deve usar.
- `environment.yml`: Configuração do [ambiente Conda](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html).
- `README.md`: Este arquivo, que fornece uma visão geral do repositório.

## Instalação e Configuração do Ambiente

Depois de clonar o repositório, siga as etapas abaixo para configurar o ambiente de desenvolvimento.

1. **Verifique se o Conda está instalado**

Abra o terminal e digite:
```shell
conda --version
```

Se o Conda estiver instalado corretamente, você verá a versão do conda exibida. Se não, você precisará instalar o Conda.

2. **Carregue o ambiente existente**

Navegue até o diretório do projeto onde o arquivo `environment.yml` está localizado. Use o seguinte comando para criar um novo ambiente conda a partir do arquivo `environment.yml`:

```shell
conda env create -f environment.yml
```

Isso criará um novo ambiente conda com todas as dependências necessárias para o projeto.

3. **Ative o ambiente**

Para ativar o ambiente, use o comando:

```shell
conda activate myenv
```

Substitua "myenv" pelo nome do ambiente que foi criado a partir do arquivo `environment.yml`.

Agora você está pronto para iniciar o desenvolvimento do projeto. Lembre-se de manter o ambiente ativado enquanto estiver trabalhando no projeto (ele desativará se você fechar o terminal). Quando terminar, você pode desativar o ambiente com o comando `conda deactivate` (ou apenas fechar o terminal).

## Como executar

(Instruções detalhadas para a execução do programa.)