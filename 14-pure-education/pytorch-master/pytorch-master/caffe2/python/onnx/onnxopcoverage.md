# Tracking why operators are not covered

[ONNX backend test script](https://github.com/onnx/onnx-caffe2/blob/master/tests/onnx_backend_test.py) reports the coverage on the operators and attributes. But we have various of reasons for the missing test coverage on operators. This doc keeps tracking why operators are not covered by the testcases.

* π The ONNX operator can map to a Caffe2 operator.
* π The solution is not perfect/finished, for example, the operator can map to a combination of Caffe2 operators.
* π Hard to find a solution with existing Caffe2 operators.

| Operator | Test Coverage | PyTorch | Caffe2 |
| :--- | :---: | :---: | :---: |
| Abs | Yes | OK | πOK |
| Acos | Yes | OK | πOK |
| Add | Yes | OK | πOK |
| And | Yes | Support int tensor, but no bool tensor | πOK |
| ArgMax |  |  | πOK |
| ArgMin |  |  | πOK |
| Asin |  |  | πOK |
| Atan |  |  | πOK |
| AveragePool |  | OK | πOK |
| BatchNormalization |  | OK | πOK |
| Cast | Yes |  | πNeed extendtion |
| Ceil | Yes |  | πOK |
| Clip | Yes | OK | πOK |
| Concat | Yes | OK | πOK |
| Constant | Yes | OK | πSpecial handling |
| Conv | Yes | OK | πOK |
| ConvTranspose | Yes |  | πOK, under enhancement |
| Cos | Yes | OK | πOK |
| DepthToSpace | Yes |  | πNo op |
| Div | Yes | OK | πOK |
| Dropout | Yes | OK | πOK |
| Elu | Yes | OK | πOK |
| Equal | Yes | OK | πOK |
| Exp | Yes | OK | πOK |
| Flatten | Yes | OK | πOK |
| Floor | Yes |  | πOK |
| GRU |  |  | π |
| Gather | Yes | OK | πC2 only support axis=0 or 1, under development |
| Gemm | Yes | OK | πC2 use FC or MatMul + Add |
| GlobalAveragePool | Yes | No direct mapping | πOK |
| GlobalLpPool |  |  | πNo mapping yet |
| GlobalMaxPool |  |  | πOK |
| Greater | Yes |  | πOK |
| HardSigmoid | Yes |  | πNo op |
| Hardmax | Yes |  | πNo op |
| InstanceNormalization |  |  | πOK |
| LRN |  | OK | πOK |
| LSTM |  |  | πOK |
| LeakyRelu | Yes | OK | πOK |
| Less | Yes |  | πOK |
| Log | Yes | OK | πOK |
| LogSoftmax |  | OK | πNo op, translated in onnx-caffe2 |
| LpNormalization |  |  | πONNX and C2 have different definition |
| LpPool |  |  | πShould be LpPool, no tests |
| MatMul | Yes | OK | πOK |
| Max | Yes | OK | πOK |
| MaxPool |  | OK | πOK |
| MaxRoiPool |  |  | πNo mapping yet |
| Mean |  |  | πOK, need broadcasting support |
| Min | Yes | OK | πOK, need broadcasting support |
| Mul | Yes | OK | πOK, need broadcasting support |
| Multinomial | Yes | OK | πno op |
| Neg | Yes | OK | πOK |
| Not | Yes |  | πOK |
| Or | Yes |  | πOK |
| PRelu | Yes | OK | πNeed to enhance C2 implementation |
| Pad | Yes | OK | πOK |
| Pow | Yes | OK | πOK |
| RNN |  |  | πOK |
| RandomNormal |  |  | πNo op |
| RandomNormalLike |  |  | πNo op |
| RandomUniform |  |  | πNo op |
| RandomUniformLike |  |  | πNo op |
| Reciprocal | Yes |  | πUse Pow to implement |
| ReduceL1 |  |  | πNo op |
| ReduceL2 |  |  | πNo op |
| ReduceLogSum |  |  | πNo op |
| ReduceLogSumExp |  |  | πNo op |
| ReduceMax |  |  | πOK |
| ReduceMean |  |  | πOK |
| ReduceMin |  |  | πOK |
| ReduceProd |  |  | πOK |
| ReduceSum |  |  | πOK |
| ReduceSumSquare |  |  | πNo op |
| Relu | Yes | OK | πOK |
| Reshape | Yes | OK | πOK |
| Selu | Yes | OK | πOK |
| Sigmoid | Yes | OK | πOK |
| Sin | Yes | OK | πOK |
| Size | Yes | OK | πOK |
| Slice | Yes | OK | πScatterAssign + Cast, very hacky implementation, Slice in C2 only supports one dimension |
| Softmax | Yes | OK | πAxis and dim has different semantics |
| Softplus | Yes | OK | πOK |
| Softsign | Yes |  | πOK |
| SpaceToDepth |  |  | πNo op |
| Split | Yes | OK | πOK |
| Sqrt | Yes |  | πOK |
| Squeeze | Yes |  | πOK |
| Sub | Yes | OK | πOK |
| Sum | Yes | OK | πOK, need broadcasting support |
| Tanh | Yes | OK | πOK |
| Tile |  | OK | πOK, need some enhance |
| TopK |  | OK | πOK |
| Transpose | Yes | OK | πOK |
| Upsample |  |  | πNo bilinear |
| Xor | Yes |  | πOK |
| experimental ATen |  |  | πOK |
| experimental Affine |  |  | πNo op |
| experimental ConstantFill |  |  | πOK |
| experimental Crop |  |  | πNo op |
| experimental FC |  |  | πOK |
| experimental GRUUnit |  |  | πOK, no tests |
| experimental GivenTensorFill |  |  | πOK |
| experimental Identity |  |  | πOK |
| experimental ImageScaler |  |  | πNo op |
| experimental MeanVarianceNormalization |  |  | πNo op |
| experimental ParametricSoftplus |  |  | πNo op |
| experimental Scale |  |  | πOK |
| experimental ScaledTanh |  |  | πNo op |
| experimental ThresholdedRelu | Yes |  | πOK |

