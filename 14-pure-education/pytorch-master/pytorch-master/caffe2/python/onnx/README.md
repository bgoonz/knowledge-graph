# README

## Caffe2 implementation of Open Neural Network Exchange \(ONNX\)

## Usage

* [ONNX to Caffe2](https://github.com/onnx/tutorials/blob/master/tutorials/OnnxCaffe2Import.ipynb)
* [Caffe2 to ONNX](https://github.com/onnx/tutorials/blob/master/tutorials/Caffe2OnnxExport.ipynb)
* [other end-to-end tutorials](https://github.com/onnx/tutorials)

## Installation

onnx-caffe2 is installed as a part of Caffe2. Please follow the [instructions](https://caffe2.ai/docs/getting-started.html) to install Caffe2.

## Folder Structure

* ./: the main folder that all code lies under
  * frontend.py: translate from caffe2 model to onnx model
  * backend.py: execution engine that runs onnx on caffe2
* tests/: test files

## Testing

onnx-caffe2 uses [pytest](https://docs.pytest.org) as test driver. In order to run tests, first you need to install pytest:

```text
pip install pytest-cov
```

After installing pytest, do

```text
pytest
```

to run tests.

Testing coverage issues/status: [https://github.com/caffe2/caffe2/blob/master/caffe2/python/onnx/ONNXOpCoverage.md](https://github.com/caffe2/caffe2/blob/master/caffe2/python/onnx/ONNXOpCoverage.md)

## Development

During development it's convenient to install caffe2 in development mode:

```text
cd /path/to/caffe2
pip install -e caffe2/
```

## License

[MIT License](https://github.com/bgoonz/Knowledge-Bank/tree/d157cab4a536be397d8f7d36c79f7d69d282500a/14-Pure-Education/pytorch-master/pytorch-master/caffe2/python/onnx/LICENSE/README.md)

