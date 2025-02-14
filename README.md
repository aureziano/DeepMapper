
## [Estimativa de Profundidade de Alta Qualidade utilizando Camera Monocular via "Adaptative Bins"](https://arxiv.org/abs/2011.14141)

## Modelos Pré-Treinados
Os modelos pré-treinados com "NYU depth v2" e "kitti" estão disponíveis [aqui](https://1drv.ms/u/s!AuWRnPR26byUmfRxBQ327hc8eXse2Q?e=AQuYZw)

## Preparando o Ambiente
* Para utilizar é necessário ter o CUDA_10.0 (e Cudnn compatível) , Python 3.5 (ou superior), pip e virtualenv (para evitar problemas)
* Certifique-se de baixar as dependencias no [link](https://1drv.ms/u/s!AuWRnPR26byUmfRbqEF7468fDdHM1g?e=KoabLc)
* Salve-as na pasta do projeto!
* Execute o comando e todas as dependências serão instaladas (processo já testado):
```
./instalar_dependencias.sh 1
```
O parametro 1 é para instalar CUDA e CUNN corretamente, se você já possuir o CUDA 10.0 e Cudnn compatível instalados então rode o seguinte comando:
```
./instalar_dependencias.sh
```

## Treinar (Precisa de uma Titan V)
* Para treinar você precisará de um login no wandb. Crie suas credenciais no site do [wandb](https://wandb.ai/site) e as memorize para utilização.
* Realize o login no terminal e inicie o treino:
```
   source venv/bin/activate
   wandb login
   python3 train.py --dataset nyu --gpus 1 --bs 4
   deactivate
```

## Testando a rede

## Visualizar imagens lado a lado - original/profundidade
* Rode o seguinte comando para utilizar um vídeo e gerar imagens lado a lado comparando o frame original e a profundidade estimada:
```
python infer_video.py --model kitti --input test_video.mp4
```
Obs.: test_video.mp4 é algum vídeo de sua escolha.

# Artigo original
[AdaBins](https://arxiv.org/abs/2011.14141)
