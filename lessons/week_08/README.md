# Analisando os resultados obtidos

Sabemos que o LeNet é realmente incrível, porem oque é bom pode se torna melhor.


* O LeNet originalmente usa a função de ativação tanh. Entretanto, podemos usar a função de ativação Relu, pois e mais simples para otimizar.
* apos uma década do surgimento do LeNet foram introduzidos o Dropout e o batch Normalization.

Nesse experimento usamos como base o código do professor [Ivanovitch Silva.](https://github.com/ivanovitchm/embedded.ai/blob/main/lessons/week_08/LeNet.ipynb) Tabem foi utilizado o Sweep do Wandb para nos auxiliar.

O experimento tem como objetivos usarmos Dropout, batch Normalization e Relu, e fazemos Comparações
![fileOne](https://github.com/PabloSanttana/IA-EMBARCADA/blob/main/lessons/week_08/imgs/Captura%20de%20tela%202022-11-09%20223428.png)

Fizemos umas modificações no LeNet:
*  model.add(Conv2D(6, (5,5) ..) ==> model.add(Conv2D(8, (5,5) ..), geralmente convoluçâo é base 2
*  model.add(BatchNormalization()) ==> Uma (normalização) logos apos, model.add(Conv2D(16, (5,5) ..)
* #model.add(Dense(84, activation='tanh')) #F6 ==> Removemos porque julgamos que já tem muitos neurônios e tambem para evitar overfit.
* Fizemos alguns Dropout logo apos Dense(120...) ==> 0.0, 0.1, 0.25

# Resultados Gráficos
 os accuracy e de val_accuracy.
 
 #### accuracy
 ![fileOne](https://github.com/PabloSanttana/IA-EMBARCADA/blob/main/lessons/week_08/imgs/accuracy.png)
 
  #### val_accuracy
 ![fileOne](https://github.com/PabloSanttana/IA-EMBARCADA/blob/main/lessons/week_08/imgs/val_accuracy.png)

# Tabela

### Ordem Maior accuracy
![fileOne](https://github.com/PabloSanttana/IA-EMBARCADA/blob/main/lessons/week_08/imgs/Captura%20de%20tela%202022-11-09%20232322.png)

### Ordem Maior val_accuracy
![fileOne](https://github.com/PabloSanttana/IA-EMBARCADA/blob/main/lessons/week_08/imgs/Captura%20de%20tela%202022-11-09%20232612.png)



Os que tiveram as menores acurácias vieram das redes com a  função de ativação tanh e com um dropout de 0.25 o uso da Normalização teve uma pequena varia nas execuções. ou seja nesse caso a Normalização  não tem muita influência em relação aos piores casos.

