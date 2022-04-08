# 첫 앱 시작, 그리고 기본적인 view 만들기

### account 앱 생성하기

* view 함수 구현할 때 `HttpResponse` 처음 써봤다
* urls.py에서 path 작성할 때 `views.hello_world` 이렇게 안써도 되나보다

`pjt01/urls.py`

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('account/', include('accountapp.urls')),
]
```

`accountapp/urls.py`

```python
from django.urls import path

from accountapp.views import hello_world

app_name = "accountapp"

urlpatterns = [
    path('hello_world/', hello_world, name='hello_world')
]
```

`accountapp/views.py`

```python
from django.http import HttpResponse
from django.shortcuts import render

# Create your views here.

def hello_world(request):
    return HttpResponse('Hello world!')
```

