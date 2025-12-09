# Segmentacao-Semantica-de-Culturas-Agricolas-com-U-Net

## 1. Introdução
Este projeto implementa uma rede neural convolucional (CNN) baseada na arquitetura **U-Net** para realizar a segmentação semântica de imagens agrícolas. O objetivo é classificar cada pixel da imagem em categorias específicas (ex: Soja, Solo/Fundo), permitindo a análise automatizada de saúde da plantação e cobertura do solo.

A implementação utiliza **TensorFlow/Keras** e foca em processamento de imagens RGB com máscaras de segmentação multiclasse.

## 2. Metodologia

### 2.1 Arquitetura U-Net
A U-Net é uma arquitetura composta por duas partes principais:
1.  **Encoder (Caminho de Contração):** Captura o contexto da imagem através de convoluções e *max pooling*, reduzindo a dimensão espacial e aumentando a profundidade dos canais.
2.  **Decoder (Caminho de Expansão):** Permite a localização precisa utilizando *convoluções transpostas* (upsampling) e concatenação com os mapas de características do encoder (*skip connections*).


### 2.2 Pipeline de Dados
O pipeline de treinamento consiste em:
* **Carregamento:** Leitura de imagens (JPG) e máscaras (PNG).
* **Pré-processamento:** Redimensionamento para 256x256 pixels e normalização (escala 0-1).
* **Formatação:** Conversão das máscaras para *One-Hot Encoding*.

## 3. Estrutura do Projeto
* `aug_data/images`: Diretório contendo as imagens de entrada.
* `aug_data/masks`: Diretório contendo as máscaras (ground truth).
* `unet_model.ipynb`: Notebook principal com treinamento e validação.

## 4. Pré-requisitos
Recomendavel a utilização de **Linux** ou em windowns a implementação utilizando o **Windows Subsystem for Linux (WSL)** para conseguir utilizar a **GPU**
Para executar este projeto, instale as dependências listadas abaixo:
```bash
pip install tensorflow numpy opencv-python matplotlib pandas
````
## 5. Instalação e Configuração do Ambiente (WSL + Ubuntu)
Para executar este projeto no Windows utilizando as melhores práticas, recomendamos o uso do WSL (Windows Subsystem for Linux). Siga as etapas abaixo:

### Passo 5.1: Instalar o WSL e Ubuntu
1.  Abra o **PowerShell** ou **Prompt de Comando** do Windows como **Administrador**.
2.  Execute o seguinte comando para instalar o WSL e a distribuição Ubuntu padrão:
    ```powershell
    wsl --install
    ```
3.  Reinicie o computador quando solicitado.
4.  Após reiniciar, abra o aplicativo "Ubuntu" no menu Iniciar. Ele finalizará a instalação e pedirá para você criar um **usuário** e **senha** para o Linux.

### Passo 5.2: Configurar Python e Pip
No terminal do Ubuntu (que você acabou de abrir), execute os comandos abaixo para atualizar o sistema e instalar o Python:

1.  Atualize os pacotes do Linux:
    ```bash
    sudo apt update && sudo apt upgrade -y
    ```
2.  Instale o Python 3, o gerenciador de pacotes (pip) e o suporte a ambientes virtuais:
    ```bash
    sudo apt install python3 python3-pip python3-venv -y
    ```

### Passo 5.3: Criar um Ambiente Virtual e Instalar o Jupyter
É recomendável isolar as bibliotecas do projeto.

1.  Crie uma pasta para o projeto e entre nela:
    ```bash
    mkdir projeto-unet && cd projeto-unet
    ```
2.  Crie um ambiente virtual chamado `venv`:
    ```bash
    python3 -m venv venv
    ```
3.  Ative o ambiente:
    ```bash
    source venv/bin/activate
    ```
    *(Você verá `(venv)` no início da linha de comando)*.

4.  Instale o Jupyter Notebook:
    ```bash
    pip install notebook
    ```

### Passo 5.4: Instalar as Dependências do Projeto
Com o ambiente ainda ativo (`(venv)`), instale as bibliotecas específicas utilizadas neste código (`tensorflow`, `opencv`, etc.):

```bash
pip install tensorflow numpy opencv-python matplotlib pandas
```
### Passo 5.5: Rode o jupyter
Com o jupyter aberto cole o arquivo e compile.
```bash
jupyter lab
```
