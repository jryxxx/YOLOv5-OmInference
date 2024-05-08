## 模型转换
- 使用 aipp.cfg 进行 ATC 模型的转换

## onnx 模型的生成
- yolo.py 文件
```python
export = True  # onnx export
```
- export.py
```python
model.model[-1].export = False  # set Detect() layer export=True
```
- 模型输入应为动态
