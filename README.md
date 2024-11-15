# Impossibility Results for Post-Compromise Security in Real-World Communication Systems

This repository contains all formal models from the paper

`Impossibility Results for Post-Compromise Security in Real-World Communication Systems`

and the means to reproduce them.

## Structure

We provide the file `AbstractModel.m4` which can be converted into Tamarin files with the `m4` preprocessor.
For convenience, we provide a `makefile` which automatically calls m4 with the appropriate parameters to generate the different models we use throughout the paper.

The `makefile` supports the following commands:
* `make` // Builds all the models into their respective folders.
* `make proofs` // For each model, prove all automatically provable results.
* `make $(X)-model` // Build only the Tamarin file for model `X`.
* `make $(X)-proofs` // Prove all automatically provable results for model `X`.

Currently, valid model names are: `base`, `non-resilient1`, `non-resilient2`, `resilient1`, `resilient2`, `sequential-sessions`, and `proposal`.
Due to the time and resources the verification of the models can take, we recommend proving each of them individually.

After building the models, you can find the following folder structure:
```
├── base
│   ├── base.spthy
├── non-resilient1
│   ├── non-resilient1.spthy
├── non-resilient2
│   ├── non-resilient2.spthy
├── resilient1
│   ├── resilient1.spthy
├── resilient2
│   ├── resilient2.spthy
├── sequential
│   ├── sequential.spthy
├── proposal
│   ├── proposal.spthy
├── proofs
│   ├── ...
├── Makefile
├── TokenPassing.spthy
└── AbstractModel.m4
```
All directories but `proofs` are named after the corresponding models they contain. The `proofs` directory contains pre-computed proofs that were either manually created or take too long to reproduce easily.
The `TokenPassing.spthy` is a specialized version of the `sequential.spthy` model. It is not automatically generated from the `AbstractModel.m4`.

------ 
