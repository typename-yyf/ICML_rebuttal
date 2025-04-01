
| Model         | bert-base     | bert-base     | bert-large    | bert-large    | gpt-2-medium  | gpt-2-medium  | gpt-2-large   | gpt-2-large   |
|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|
| Steps         | @50k step     | @100k step    | @50k step     | @100k step    | @100k step    | @200k step    | @100k step    | @200k step    |
| Small LR      | 0.02%             | 0.03%   | 0.03%          | 0.03%         | 0.05%           | 0.03%          | 0.06%           | 0.05%       |
| Large LR      | 0.09%            | 0.06%            | 0.16%  | %0.11      | %0.23   | %0.15        | %0.19 | %0.15     |

Table R.1: Frequency of PSS activation across different settings.


|Model|BERT-large|BERT-large|GPT-2-Large|GPT-2-large|GPT-2-XL|GPT-2-XL|GPT-2-XL|
|----|----------|----------|-----------|-----------|--------|--------|--|
|LR   |5e-5|1e-4|5e-5|1e-4|1e-5|5e-5|1e-3|
|naive|0/2 2.4±0.1|2/2 -|0/1 3.9|1/1 -|0/2 3.8±0.1|2/2 -|1/1 -|
|gc|-|0/2 2.9±0.1|-|0/2 5.2±0.3|-|0/1 4.2|1/1 -|
|or|-|3/3 -|-|1/1 -|-|1/1 -|1/1 -|
|qk-norm|-|0/2 2.9±0.2|-|1/1 -|-|0/1 3.9|1/2 4.5|
|pss|0/2 2.4±0.1|0/2 2.7±0.1|0/1 4.0|0/1 4.2|0/1 3.8|0/1 3.9|0/2 4.6|

Table R.2: Supplementary experiments to Table 6 of the original paper, comparing the performance of different stabilization methods on model stability under high learning rates.


|Hyper-parameters|Batch size|Batch size|LR Warmup steps|LR Warmup steps
|--|--|--|--|--|
||64|1|1000|1|
|Naive|0/3 3.0±0.2|4/4 -|0/3 3.0±0.2|3/3 -|
|gc|-|0/1 3.2|-|0/1 3.0|
|or|-|0/2 4.0±0.1|-|1/1 -|
|qk-norm|-|0/2 3.3±0.1|-|2/2 -|
|pss|0/3 3.0±0.1|0/4 3.4±0.2|0/3 3.0±0.2|0/3 2.9±0.1|

Table R.3: Supplementary experiments to Table 7 of the original paper, comparing the performance of different stabilization methods on model stability under inappropriate hyper-parameter settings.


|Tasks|Test loss|CoLA(acc)|SST-2(acc)|MRPC(acc)|MNLI(acc)|
|--|--|--|--|--|--|
|Naive @ 100k steps(lr=1e-4)|3.05|50.8%|85.2%|82.4%|81.6%|
|PSS @ 70k steps(lr=2e-4)|2.92|51.0%|85.8%|81.7%|82.5%|
|PSS @ 70k steps(lr=4e-4)|2.84|52.3%|86.1%|84.6%|81.9%|

Table R.4:
