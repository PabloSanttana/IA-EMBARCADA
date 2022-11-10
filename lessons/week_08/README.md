# Analisando os resultados obtidos

Sabemos que o LeNet é realmente incrível, porem oque é bom pode se torna melhor.


* O LeNet originalmente usa a função de ativação tanh. Entretanto, podemos usar a função de ativação Relu, pois e mais simples para otimizar.
* apos uma década do surgimento do LeNet foram introduzidos o Dropout e o batch Normalization.

Nesse experimento usamos como base o código do professor [Ivanovitch Silva.](https://github.com/ivanovitchm/embedded.ai/blob/main/lessons/week_08/LeNet.ipynb) Tabem foi utilizado o Sweep do Wandb para nos auxiliar.

O experimento tem como objetivos usarmos Dropout, batch Normalization e Relu, e fazemos Comparações
