
## 框架 Pytest + Selenium + allure

安装环境依赖 pip install -r requirements.txt






## pytest 插件安装

多线程运行

    pip install pytest-xdist

失败用例重跑

    pip install pytest-rerunfailures 

报告生成

    pip install pytest-html 

    pip install allure-pytest allure

用例执行顺序

    pip install pytest-ordering 

    用法:@pytest.mark.run(order=Num)

---

## pytest 参数

-n ：使用该命令后，将多个线程执行用例 pytest -n 3

--reruns ：使用该命令后，将失败的用例重新执行 pytest --reruns 3
    
-q ：使用该命令后，将显示简单的结果（pytest -q）

-s ：使用该命令后，将用例的信息打印出来 （pytest -s）

-x ： 遇到错误时停止测试 （pytest -x）

-maxfail ： 当用例错误个数达到指定数量时，停止测试 pytest --maxfail 2


   

## pytest.ini 配置

    [pytest]
    addopts = -s -q --html= report.html     # 命令行执行 默认带参
    markers = bvt: bvt测试用例              # 冒号写入标记说明
    
    # markes用法
    @pytest.mark.bvt    # 标记用例   
    pytest -m bvt       # 运行标记bvt
    
---

## allure 生成报告

1、安装插件 pip install allure-pytest

2、PATH路径配置环境变量 allure-2.13.8/bin

3、以管理员身份运行PyCharm

4、生成XML格式的内容并指定目录 

    pytest test_pytest.py --alluredir ./allure-results --clean-alluredir      

5、将XML格式的内容转为HTML格式的内容

    allure generate allure-results -o allure_report/html --clean

6、若需要指定某些级别、某些模块单独执行用例

    --allure-serverities blocker 指定[标记级别为“阻塞”]用例执行 

    --allure-feature = '登录模块' 指定[标记模块为“登录模块”]用例执行


