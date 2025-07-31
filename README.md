# Como instalar o `aptitude` no `Linux Ubuntu`

## Resumo

Este documento apresenta os passos necessários para instalar o utilitário `aptitude` no `Linux Ubuntu`.

## _Abstract_

_This document shows the steps required to install the `aptitude` utility on `Linux Ubuntu`._

## Descrição [2]

### `aptitude`

O `aptitude` é uma interface mais amigável (com modo texto interativo) para gerenciar pacotes no Debian e derivados (como Ubuntu), podendo substituir comandos como `apt`, `apt-get` e `dpkg` em muitas situações.


## 1. Instalar o `aptitude` no `Linux Ubuntu`

Para instalar o `aptitude`, siga os passos abaixo:

1. Abra o `Terminal Emulator`. Você pode fazer isso pressionando: `Ctrl + Alt + T`

2. Certifique-se de que seu sistema esteja limpo e atualizado.

    2.1 Limpar o `cache` do gerenciador de pacotes `apt`. Especificamente, ele remove todos os arquivos de pacotes (`.deb`) baixados pelo `apt` e armazenados em `/var/cache/apt/archives/`. Digite o seguinte comando:
    ```bash
    sudo apt clean
    ```

    2.2 Remover pacotes `.deb` antigos ou duplicados do `cache` local. É útil para liberar espaço, pois remove apenas os pacotes que não podem mais ser baixados (ou seja, versões antigas de pacotes que foram atualizados). Digite o seguinte comando:
    ```bash
    sudo apt autoclean
    ```

    2.3 Remover pacotes que foram automaticamente instalados para satisfazer as dependências de outros pacotes e que não são mais necessários. Digite o seguinte comando:
    ```bash
    sudo apt autoremove -y
    ```

    2.4 Buscar as atualizações disponíveis para os pacotes que estão instalados em seu sistema. Digite o seguinte comando e pressione `Enter`:
    ```bash
    sudo apt update
    ```

    2.5 **Corrigir pacotes quebrados**: Isso atualizará a lista de pacotes disponíveis e tentará corrigir pacotes quebrados ou com dependências ausentes:
    ```bash
    sudo apt --fix-broken install
    ```

    2.6 Limpar o `cache` do gerenciador de pacotes `apt` novamente:
    ```bash
    sudo apt clean
    ```

    2.7 Para ver a lista de pacotes a serem atualizados, digite o seguinte comando e pressione `Enter`:
    ```bash
    sudo apt list --upgradable
    ```

    2.8 Realmente atualizar os pacotes instalados para as suas versões mais recentes, com base na última vez que você executou `sudo apt update`. Digite o seguinte comando e pressione `Enter`:
    ```bash
    sudo apt full-upgrade -y
    ```

3. Instale o `aptitude` e verifique a instalacao:
    ```bash
    sudo apt update
    sudo apt install aptitude
    aptitude --version
    ```

4. (Opcional) Execute a interface TUI:
    ```bash
    sudo aptitude
    ```

## Referências

[1] OPENAI. ***Instalar aptitude no Linux Ubuntu***. Disponível em: <https://chatgpt.com/c/688ab781-f5d8-8333-b286-87da568cea0e>. ChatGPT. Acessado em: 31/07/2025 00:40.
