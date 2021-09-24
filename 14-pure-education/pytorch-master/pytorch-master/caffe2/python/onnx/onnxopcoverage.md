# Tracking why operators are not covered

[ONNX backend test script](https://github.com/onnx/onnx-caffe2/blob/master/tests/onnx_backend_test.py) reports the coverage on the operators and attributes. But we have various of reasons for the missing test coverage on operators. This doc keeps tracking why operators are not covered by the testcases.

* 💚 The ONNX operator can map to a Caffe2 operator.
* 💛 The solution is not perfect/finished, for example, the operator can map to a combination of Caffe2 operators.
* 💔 Hard to find a solution with existing Caffe2 operators.

| Operator | Test Coverage | PyTorch | Caffe2 |
| :--- | :---: | :---: | :---: |
| Abs | Yes | OK | 💚OK |
| Acos | Yes | OK | 💚OK |
| Add | Yes | OK | 💚OK |
| And | Yes | Support int tensor, but no bool tensor | 💚OK |
| ArgMax |  |  | 💚OK |
| ArgMin |  |  | 💚OK |
| Asin |  |  | 💚OK |
| Atan |  |  | 💚OK |
| AveragePool |  | OK | 💚OK |
| BatchNormalization |  | OK | 💚OK |
| Cast | Yes |  | 💔Need extendtion |
| Ceil | Yes |  | 💚OK |
| Clip | Yes | OK | 💚OK |
| Concat | Yes | OK | 💚OK |
| Constant | Yes | OK | 💛Special handling |
| Conv | Yes | OK | 💚OK |
| ConvTranspose | Yes |  | 💚OK, under enhancement |
| Cos | Yes | OK | 💚OK |
| DepthToSpace | Yes |  | 💔No op |
| Div | Yes | OK | 💚OK |
| Dropout | Yes | OK | 💚OK |
| Elu | Yes | OK | 💚OK |
| Equal | Yes | OK | 💚OK |
| Exp | Yes | OK | 💚OK |
| Flatten | Yes | OK | 💚OK |
| Floor | Yes |  | 💚OK |
| GRU |  |  | 💚 |
| Gather | Yes | OK | 💛C2 only support axis=0 or 1, under development |
| Gemm | Yes | OK | 💛C2 use FC or MatMul + Add |
| GlobalAveragePool | Yes | No direct mapping | 💚OK |
| GlobalLpPool |  |  | 💔No mapping yet |
| GlobalMaxPool |  |  | 💚OK |
| Greater | Yes |  | 💚OK |
| HardSigmoid | Yes |  | 💔No op |
| Hardmax | Yes |  | 💔No op |
| InstanceNormalization |  |  | 💚OK |
| LRN |  | OK | 💚OK |
| LSTM |  |  | 💚OK |
| LeakyRelu | Yes | OK | 💚OK |
| Less | Yes |  | 💚OK |
| Log | Yes | OK | 💚OK |
| LogSoftmax |  | OK | 💚No op, translated in onnx-caffe2 |
| LpNormalization |  |  | 💔ONNX and C2 have different definition |
| LpPool |  |  | 💚Should be LpPool, no tests |
| MatMul | Yes | OK | 💚OK |
| Max | Yes | OK | 💚OK |
| MaxPool |  | OK | 💚OK |
| MaxRoiPool |  |  | 💔No mapping yet |
| Mean |  |  | 💚OK, need broadcasting support |
| Min | Yes | OK | 💚OK, need broadcasting support |
| Mul | Yes | OK | 💚OK, need broadcasting support |
| Multinomial | Yes | OK | 💔no op |
| Neg | Yes | OK | 💚OK |
| Not | Yes |  | 💚OK |
| Or | Yes |  | 💚OK |
| PRelu | Yes | OK | 💛Need to enhance C2 implementation |
| Pad | Yes | OK | 💚OK |
| Pow | Yes | OK | 💚OK |
| RNN |  |  | 💚OK |
| RandomNormal |  |  | 💔No op |
| RandomNormalLike |  |  | 💔No op |
| RandomUniform |  |  | 💔No op |
| RandomUniformLike |  |  | 💔No op |
| Reciprocal | Yes |  | 💚Use Pow to implement |
| ReduceL1 |  |  | 💔No op |
| ReduceL2 |  |  | 💔No op |
| ReduceLogSum |  |  | 💔No op |
| ReduceLogSumExp |  |  | 💔No op |
| ReduceMax |  |  | 💚OK |
| ReduceMean |  |  | 💚OK |
| ReduceMin |  |  | 💚OK |
| ReduceProd |  |  | 💚OK |
| ReduceSum |  |  | 💚OK |
| ReduceSumSquare |  |  | 💔No op |
| Relu | Yes | OK | 💚OK |
| Reshape | Yes | OK | 💚OK |
| Selu | Yes | OK | 💚OK |
| Sigmoid | Yes | OK | 💚OK |
| Sin | Yes | OK | 💚OK |
| Size | Yes | OK | 💚OK |
| Slice | Yes | OK | 💔ScatterAssign + Cast, very hacky implementation, Slice in C2 only supports one dimension |
| Softmax | Yes | OK | 💔Axis and dim has different semantics |
| Softplus | Yes | OK | 💚OK |
| Softsign | Yes |  | 💚OK |
| SpaceToDepth |  |  | 💔No op |
| Split | Yes | OK | 💚OK |
| Sqrt | Yes |  | 💚OK |
| Squeeze | Yes |  | 💚OK |
| Sub | Yes | OK | 💚OK |
| Sum | Yes | OK | 💚OK, need broadcasting support |
| Tanh | Yes | OK | 💚OK |
| Tile |  | OK | 💛OK, need some enhance |
| TopK |  | OK | 💚OK |
| Transpose | Yes | OK | 💚OK |
| Upsample |  |  | 💛No bilinear |
| Xor | Yes |  | 💚OK |
| experimental ATen |  |  | 💚OK |
| experimental Affine |  |  | 💔No op |
| experimental ConstantFill |  |  | 💚OK |
| experimental Crop |  |  | 💔No op |
| experimental FC |  |  | 💚OK |
| experimental GRUUnit |  |  | 💚OK, no tests |
| experimental GivenTensorFill |  |  | 💚OK |
| experimental Identity |  |  | 💚OK |
| experimental ImageScaler |  |  | 💔No op |
| experimental MeanVarianceNormalization |  |  | 💔No op |
| experimental ParametricSoftplus |  |  | 💔No op |
| experimental Scale |  |  | 💚OK |
| experimental ScaledTanh |  |  | 💔No op |
| experimental ThresholdedRelu | Yes |  | 💚OK |

