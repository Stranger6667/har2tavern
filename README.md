# HAR2tavern

[tavern](https://github.com/taverntesting/tavern) 是一个pytest插件，用来进行接口自动化测试，通过**YAML**来描述和管理测试用例。
尽管YAML已经十分简洁，但是的接口数量很多时，创建YAML文件依然耗时。

本工具将通过抓包获取到的HAR文件，快速生成tavern所支持的YAML文件，实现快速进行接口自动化的目的。

当然，你也可以对生成的YAML进行修改，以实现复杂业务的测试。


## 安装
```bash
pip install har2tavern
```



## 使用

1. 基本用法
    ```bash
    >har2tavern file.harhar2
    
    Output file: ./test_api_1.tavern.yaml
    Output file: ./test_api_2.tavern.yaml
    Output file: ./test_api_3.tavern.yaml
    Output file: ./test_api_4.tavern.yaml
    Output file: ./test_api_5.tavern.yaml
    Output file: ./test_api_6.tavern.yaml
    Output file: ./test_api_7.tavern.yaml
    Successfully generated 7 files
    
    ```
    本命令将生成多个yaml格式的测试用例
    
2. 更多参数

    ```bash
    >har2pytest --help
    Usage: har2pytest [OPTIONS] HARFILE
    根据har文件，生成yaml格式的接口自动化测试用例

    Options:
      -H, --host TEXT            只为指定的host生成用例
      -S, --single-file BOOLEAN  将用例合并到单个文件
      --help                     Show this message and exit.
    ```




## 开发
1. 获取源代码
    ```bash
    git clone https://github.com/dongfangtianyu/har2tavern.git
    cd har2tavern
    ```
2. 创建venv，并安装依赖
    ```bash
    python -m venv venv
    source ~/venv/bin/activate
    pip install -r requirements.txt
    pre-commit install
    ```
3. 执行测试、 执行检查
    ```bash
    pytest && pre-commit run --all-files
    ```

    在写代码之前，要确定你获取的代码是没有问题的,所有先执行一次测试

5. 开发代码
    ```
    coding....
   ```
    现在，你可以尽情的编码了。

6. 执行测试 、 执行检查

    > 特别提醒你在提交代码之前，再次进行测试和检查
    ```bash
    pytest && pre-commit run --all-files
    ```

7. 打包

    ```
    python setup.py sdist
    ```
    执行该命令将在 `./dist`目录下中生成安装包，可以分发、安装



## 贡献

如果你对本工具有更好的想法，欢迎发起PR https://github.com/dongfangtianyu/har2tavern

我们希望PR中有修改的描述、测试用例，并且所有用例全部测试通过。
