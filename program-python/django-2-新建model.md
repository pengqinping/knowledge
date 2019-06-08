# Django 数据模型

## 每一个Python的 class 就对应数据库中的一张表
投票中创建两个模型：Question 和 Choice

```python
# polls/models.py
class Question(models.Model):
    question_text = models.CharField(max_length=200)
    pub_date = models.DateField('date published')
    
class Choice(models.Model):
    question = models.ForeignKey(Question, on_delete=models.CASCADE)
    choice_text = models.CharField(max_length=200)
    votes = models.IntegerField(default=0)

```

## 启用模型

```python
# firstDjango/setting.py
INSTALLED_APP = [
    # 新增polls
    'polls'
]
```
* 根据Model 生成 Migration *对应文件polls/0001_initial.py*
`python manage.py makemigrations polls`
* 生成SQL
`python manage.py sqlmigrate polls 0001`
* 将操作同步到数据库
`python manage.py migrate`

## 修改模型三部曲
修改模型时的操作分三步
* 在models.py中修改模型；
* 运行**python manage.py makemigrations**为改动创建迁移记录；
* 运行**python manage.py migrate**，将操作同步到数据库。

## 模型API 交互式的数据库操作
* 命令行 `python manage.py shell`

常用操作：

```python
1. import django
2. django.setup()
3. from poll.model import Question, Choice # 导入model
4. # 直接操作model
Question.objects.all()

```