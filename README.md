# Introdução
### Ferramentas de Brute Force:

**Medusa →** Utilizada para vários protocolos. É Multithread, realiza várias tentativas simultaneamente e  possui alto desempenho . É personalizável para situações mais específicas apesar de não ter uma performance boa na WEB.

**Hydra →** Ferramenta de Brute Force baseada em rede que tem compatibilidade com muitos protocolos. Indicada para testes de serviço exposto de uma infraestrutura de modo online, não sendo tão eficaz no offline. 

**Ncrack →** Da mesma equipe que mantém o Nmap. Seu diferencial é a otimização para latência de rede e largura de banda, ideal para redes maiores. Seu ponto fraco é lidando com a WEB. 

**John →** Específico para ambientes offline, quando já possuímos o hash da senha e é preciso descobrir ela a partir disso. Ideal para auditorias internas ou para análise forense. Não interage com serviços online

**Wpscan →** Foca em auditar instalações do wordpress.

**Patator →** É uma ferramenta mais complexa por ser personalizável 

- Tipos de autenticação
    
    Depois que você faz login, o sistema precisa **te reconhecer nas próximas páginas** (tipo quando você abre o feed, manda mensagem, etc.), a partir daí que cada tipo de autenticação vai se diferenciar.
    
    - **Sem estado →** Cada requisição precisa **enviar todas as informações necessárias** (Token ) para validar a identidade do usuário, não possui nenhuma informação guarada, ele apenas valida o Token em todas as requisições.
    - **Com estado →**  O servidor **mantém o estado da sessão** do usuário normalmente guardando um **identificador de sessão** em memória, banco ou cache (cookie), toda vez que é necessário fazer uma autenticação esse cookie é verificado. Autenticação comum em sites.
    - **Autenticação federada →** Em vez de o sistema autenticar o usuário diretamente, ele **confia em um provedor externo de identidade** (como Google, Microsoft, Facebook, etc.).
- Tipos de ataque de força bruta
    - **Dicionário →** usa arquivos de texto que contém várias combinações de senhas comuns já prontas
    - **Permutação →** Tenta todas as combinações dos caracteres de forma aleatória e cresce de forma exponencial dependendo do tamanho da senha
    - **Ataque híbrido →** Combina os dois ataques para melhor performance, tem um alto índice de sucesso:
        - **Mangling Rules →** Utiliza um arquivo com senhas comuns mas modifica alguns caracteres de forma inteligente e aleatória, como trocar o A pelo 4, S por $…
        - **Junção de listas →** Testa todas as combinações possíveis entre listas, juntando elas.
    - **Password Spraying →** Ao invés de testar várias senhas em um usuário, testa uma mesma senha em vários usuários apenas uma vez por usuário, para tentar burlar os sistemas contra força bruta que detectam comportamento anormal.
    - **Credentiual Stuffing →** Coleta dados já vazados de um usuário para fazer a força bruta em vários sistemas.
