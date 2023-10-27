# Image-Generator-Tensorflow

<img src="Image_Generator.png"/>

Este é um exemplo simples de código que demonstra como usar o TensorFlow e a biblioteca Keras-CV para gerar imagens a partir de descrições de texto usando o modelo StableDiffusion. O código também utiliza o Matplotlib para exibir as imagens geradas.

## Pré-requisitos
- Python 3.x
- TensorFlow
- Keras-CV
- Matplotlib
## Instalação
Antes de executar o código, certifique-se de ter as bibliotecas necessárias instaladas. Você pode instalá-las usando o seguinte comando pip:

```bash
pip install tensorflow keras_cv --upgrade --quiet
```

## Explicação do Código
Importar as bibliotecas necessárias:

```python
import time
import keras_cv
from tensorflow import keras
import matplotlib.pyplot as plt
```
Criar um modelo StableDiffusion com uma largura e altura de imagem específicas:

```python
model = keras_cv.models.StableDiffusion(img_width=512, img_height=512)
```
Gerar imagens a partir de uma descrição de texto:

```python
images = model.text_to_image("fotografia de um robô na praia", batch_size=3)
```
Definir uma função para exibir as imagens geradas:

```python
def plot_images(images):
    plt.figure(figsize=(20, 20))
    for i in range(len(images)):
        ax = plt.subplot(1, len(images), i + 1)
        plt.imshow(images[i])
        plt.axis("off")
```
Chamar a função plot_images para exibir as imagens geradas:

```python
plot_images(images)
```

<img src="robots_in_the_beach.png"/>

## Uso
- Certifique-se de ter instaladas as bibliotecas necessárias, conforme mencionado na seção "Instalação".

- Copie e cole o código em um script Python ou em um Jupyter Notebook.

- Execute o script. Ele irá gerar e exibir imagens com base na descrição de texto fornecida.

### Notas
Você pode modificar a descrição de texto e o tamanho do lote (batch size) de acordo com suas necessidades.
Este exemplo demonstra como usar o modelo StableDiffusion do Keras-CV para gerar imagens a partir de descrições de texto usando o TensorFlow. Sinta-se à vontade para explorar e adaptar o código para suas necessidades específicas.
