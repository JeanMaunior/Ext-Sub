# Separate the Wheat from the Chaff: Model Deficiency Unlearning via Parameter-Efficient Module Operation


<div align="center">

 [Overview](https://github.com/JeanMaunior/Ext-Sub#sparkles-overview) | [Usage](https://github.com/JeanMaunior/Ext-Sub#rotating_light-usage) | [Citation](https://github.com/JeanMaunior/Ext-Sub#cite) | [License](https://github.com/JeanMaunior/Ext-Sub#license)

</div>



## :sparkles: Overview
<p align="center">
  <img src="figure/ext-sub.png" width="650"/>
</p>

Code for the paper ["Separate the Wheat from the Chaff: Model Deficiency Unlearning via Parameter-Efficient Module Operation"](https://arxiv.org/abs/2308.08090).



## :rotating_light: Usage

### Environment

```
conda create -n EXT-SUB python=3.10
conda activate EXT-SUB
pip install -r requirements.txt
```


### Train
Run the training Bash script with custom parameters: `model_name_or_path`, `data_path`, `output_dir`
```
cd training
bash train_peft.sh
```
⚠️ tips: The training code from Alpaca was leveraged in order to resize the embedding of models, thereby incorporating a pad token. When saving the tokenizer after training, it now includes the pad token, which is not present in the original model (as only the PEMs were saved). To effectively utilize the pad token during testing, it is advisable to either resize the embedding once more or substitute the pad token with an existing token.


### PEMs Operation
```
python ext_sub.py \
  --input_path_1  Your/Expert/PEMs/Path \
  --input_path_2  Your/Anti-Expert/PEMs/Path \
  --alpha 1.0 \
  --method ext-sub \
  --output_path  Your/Output/PEMs/Path
```



## Cite

```
@article{hu2023separate,
  title={Separate the Wheat from the Chaff: Model Deficiency Unlearning via Parameter-Efficient Module Operation},
  author={Hu, Xinshuo and Li, Dongfang and Zheng, Zihao and Liu, Zhenyu and Hu, Baotian and Zhang, Min},
  journal={arXiv preprint arXiv:2308.08090},
  year={2023}
}
```



## License
This repository respects to Apache license 2.0.