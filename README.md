# gitconflixtro

Praticando resolução de conflitos.

## Feedback

Certo, vamos lá.

Os passos 1 e 2 da segunda atividade do módulo 2 não influenciam o fluxo de trabalho para a resolução de conflitos.

O passo 3 é a criação do diretório e repositório. Até aqui, não há grandes problemas, e existem diversas maneiras de fazer. A minha preferida para começar um projeto é criar um diretório local, configurar localmente e depois publicar no GitHub ou GitLab. Para projetos já existentes, a opção de clonar e configurar via SSH é a que menos dá problemas.

O passo 4 é onde ocorre o primeiro merge, que pode ser visto nas duas primeiras telas. Não há grandes problemas aqui. A observação a ser feita é que não haverá conflito, pois ao realizar o merge, a última alteração feita na branch secundária é que irá prevalecer.

Agora, na atividade 3, começamos a gerar conflitos para testarmos 3 métodos de resolução.

Primeiro método: via merge mesmo. Após realizar a modificação em ambas as branches, ao realizar o merge, existem 3 possibilidades: escolher entre uma das modificações, manter ambas ou sobrescrevê-las. A ponderação aqui é que não é necessário fazer um commit dessas alterações para realizar o merge, como mostrado no exercício.

Segundo método: utilizando rebase. O rebase é feito na branch secundária criada e não na master. Para fazer um rebase na master, você deve estar na master e usar git rebase branch-alvo. Referência tirada da documentação do git👇🏻

Basic Rebase
To perform a basic rebase, you can use the following commands:
```bash
$ git checkout <branch-to-rebase>
$ git rebase <target-branch>
```

Aqui, achei bem estranho, pois alguns comentários davam a entender que ambas as branches ficariam "iguais" (isso só ocorreria se você sobrescrever com o conteúdo da master durante o rebase) ou que essa sequência iria realizar o rebase na master.

Por fim, o terceiro método: git stash. Ele segue o mesmo princípio do rebase, permitindo que você saia de uma branch sem salvar em um commit o trabalho feito e volte para ela para continuar do estado em que parou. Assim como o rebase, as alterações são feitas na branch secundária e não na master.

Observações importantes:

- os commits após organizar as alterações não são obrigatórios. A exceção é se você fizer uma modificação diferente das apresentadas.

    → Motivo: isso pode causar duplicação desnecessária de commits.

- os comandos rebase e stash são, de fato, mais utilizados nas ramificações secundárias, então entender a vantagem deles te possibilita um leque maior do que simplesmente usar merge sempre que precisar atualizar recursos da branch principal.

- todas as branches criadas são enviadas ao repositório remoto, informação que não é feita na descrição dos exercícios.

- por fim, veja o git switch (a partir da versão 2.23), que foca exclusivamente na troca de branches.
