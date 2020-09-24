# alex


## Execução

### Forma mais simples
```bash
~/alex $ make  # ou make install
~/alex $ alex <arquivo-fonte>
```
Porém isso instala a aplicação para o usuário e exige que depois se faça:
```bash
~/alex $ make clean  # que desinstala a aplicação e a biblioteca de que depende
```

### Forma mais limpa
```bash
~/alex $ python3 -m venv .venv  # cria um ambiente virtual dentro do diretório '.venv'
~/alex $ source .venv/bin/activate  # ativa o ambiente virtual alterando o PATH para apontar para o 'python' e 'pip' internos
~/alex $ pip3 install .  # instala no ambiente virtual o pacote que se encontra nesse diretório e suas dependências
~/alex $ alex <arquivo-fonte>
```
Depois basta remover o diretório e o resto do sistema permanece intocado.
Talvez seja importante executar `deactivate` no shell para restaurar o PATH (ou simplesmente iniciar outra sessão do shell).

## Execução em Windows (caso ocorra problema para criar o ambiente virtual)
```bash
C:\CAMINHO\alex> pip install .
C:\CAMINHO\alex> alex <arquivo-fonte>
```

### Exemplo
```bash
C:\CAMINHO\alex> alex primes.ccc
```

## Resolução de problemas

### Não encontrou `setup.py`
Sua versão do `pip` é mais antiga e ainda exige a presença de um arquivo `setup.py`. A solução é instalar a biblioteca com `pip install --user sly` e depois executar a aplicação com `python3 alex <arquivo-fonte>`. Você pode desinstalar a biblioteca com `pip uninstall sly` quando não for mais usar a aplicação.

### Não encontrou módulo `venv`
Sua distribuição retirou esse módulo do pacote do Python, e você precisa instalá-lo separadamente, possivelmente sob o nome `python3-venv`.
