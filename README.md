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
Para executar este projeto, instale as dependências listadas abaixo:

```bash
pip install tensorflow numpy opencv-python matplotlib pandas
