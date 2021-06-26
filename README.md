# mlflow-tutorial

## Installing
Install MLflow from PyPI via `pip install mlflow`

MLflow requires `conda` to be on the `PATH` for the projects feature.

## Launching the Tracking UI
The MLflow Tracking UI will show runs logged in `./mlruns` at http://localhost:5000. Start it with:

```bash
mlflow ui
```

## Running a Project from a URI
The `mlflow run` command lets you run a project packaged with a MLproject file from a local path or a Git URI:

```bash
mlflow run examples/sklearn_elasticnet_wine -P alpha=0.4
mlflow run https://github.com/mlflow/mlflow-example.git -P alpha=0.4
```
See `examples/sklearn_elasticnet_wine` for a sample project with an MLproject file.

## Saving and Serving Models

```bash
mlflow models serve -m [model_dir] -p [port]
```

## Inference

```bash
curl --location --request POST 'localhost:1234/invocations' \
-H 'Content-Type: application/json' \
-d '{
    "columns":["sepal length (cm)", "sepal width (cm)", "petal length (cm)",  "petal width (cm)"],
    "data": [[5.1, 3.5, 1.4, 0.2]]
}'
```