# Flower Cross-evaluation example with TensorFlow/Keras and `start_simulation`

This introductory example uses the simulation capabilities of Flower to simulate a set of clients a
single machine. Clients models are then cross-evaluated using the `client.evaluate` function.

## Context of the example

This example is intended to demonstrate how to use the `client.evaluate` function to allow
cross-evaluation bewteen clients. Therefore, we consider an artificial use case of the MNIST
dataset, where clients dataset only contains a few digits. Therefore, averaging the weights of the
models would produce a model that is not able to classify all digits. In this case, cross-evaluation
allows clients to identify other models that are able to classify a digit that they have.

## Running the example (via Poetry)

Start by cloning the code example. We prepared a single-line command that you can copy into your
shell which will checkout the example for you:

```shell
git clone --depth=1 https://github.com/adap/flower.git && mv flower/examples/cross_evaluation . && rm -rf flower && cd cross_evaluation
```

This will create a new directory called `cross_evaluation` containing the following files:

```text
-- README.md       <- Your're reading this right now
-- sim.ipynb       <- Example notebook
-- sim.py          <- Example code
-- pyproject.toml  <- Example dependencies (for Poetry)
```

Project dependencies (such as `tensorflow` and `flwr`) are defined in `pyproject.toml` (the modern
alternative to `requirements.txt`). We recommend [Poetry](https://python-poetry.org/docs/) to
install those dependencies and manage your virtual environment ([Poetry
installation](https://python-poetry.org/docs/#installation)), but feel free to use a different way
of installing dependencies and managing virtual environments if you have other preferences.

```shell
poetry install
```

Poetry will install all your dependencies in a newly created virtual environment. To verify that
everything works correctly you can run the following command:

```shell
poetry run python3 -c "import flwr"
```

If you don't see any errors you're good to go! 

```bash
poetry run python sim.py
```
