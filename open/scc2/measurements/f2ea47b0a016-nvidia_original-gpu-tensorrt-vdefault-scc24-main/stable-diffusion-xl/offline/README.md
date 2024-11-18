This experiment is generated using the [MLCommons Collective Mind automation framework (CM)](https://github.com/mlcommons/cm4mlops).

*Check [CM MLPerf docs](https://docs.mlcommons.org/inference) for more details.*

## Host platform

* OS version: Linux-6.1.0-27-amd64-x86_64-with-glibc2.29
* CPU version: x86_64
* Python version: 3.8.10 (default, Sep 11 2024, 16:02:53) 
[GCC 9.4.0]
* MLCommons CM version: 3.3.3

## CM Run Command

See [CM installation guide](https://docs.mlcommons.org/inference/install/).

```bash
pip install -U cmind

cm rm cache -f

cm pull repo mlcommons@cm4mlops --checkout=f72ffc1c4ac088b2f78855b05b3ade8ffb2ca497

cm run script \
	--tags=run-mlperf,inference,_r4.1-dev,_short,_scc24-main \
	--model=sdxl \
	--implementation=nvidia \
	--framework=tensorrt \
	--category=datacenter \
	--scenario=Offline \
	--execution_mode=test \
	--device=cuda \
	--min_query_count=528 \
	--adr.nvidia-harness.use_graphs=True \
	--adr.nvidia-harness.gpu_inference_streams=4 \
	--adr.nvidia-harness.gpu_copy_streams=2 \
	--rerun \
	--clean \
	--quiet
```
*Note that if you want to use the [latest automation recipes](https://docs.mlcommons.org/inference) for MLPerf (CM scripts),
 you should simply reload mlcommons@cm4mlops without checkout and clean CM cache as follows:*

```bash
cm rm repo mlcommons@cm4mlops
cm pull repo mlcommons@cm4mlops
cm rm cache -f

```

## Results

Platform: f2ea47b0a016-nvidia_original-gpu-tensorrt-vdefault-scc24-main

Model Precision: int8

### Accuracy Results 
`CLIP_SCORE`: `16.6316`, Required accuracy for closed division `>= 31.68632` and `<= 31.81332`
`FID_SCORE`: `234.62921`, Required accuracy for closed division `>= 23.01086` and `<= 23.95008`

### Performance Results 
`Samples per second`: `7.46497`
