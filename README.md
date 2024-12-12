# Follow the below and execute one by one.
## Clone the repo
git clone https://github.com/amelamedolli/Amel.git

## Install the libraries
pip install aiohttp numpy tqdm pytest datasets torch transformers


cd ../Amel


mkdir tutorial


## If you want to do 20 completion for each sample for all the coding problems
python3 automodel.py --name "facebook/incoder-6B" --root-dataset humaneval --lang java --temperature 0.2 --batch-size 20 --completion-limit 20 --output-dir-prefix tutorial

cd ../evaluation/src

## Evaluate
python3 main.py --dir ../code_generation/tutorial --output-dir ../code_generation/tutorial --recursive


cd ../


cd ../

## Get the functional correctness score
python3 pass_k.py ./tutorial/*

