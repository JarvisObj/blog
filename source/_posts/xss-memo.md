title: xss ����¼
categories:
  - ��ȫ
date: 2015-04-27 17:10:00
---

����ҵ��Ӧ�üܹ������ſ����ᵽ��xss���������һЩ���õ���������������

<!--more-->

## Cheat Sheet ##

http://drops.wooyun.org/tips/1955

## ɨ�蹤�� ##

![](http://image.webreader.duokan.com/mfsv2/download/s010/p01c8C61NADB/bllx3WsLhjwNrS.jpg)

## ���˺��� ##

��Ҫ��ת��and��С�ںš����ںź��������š�

```
function htmlEnco(s)
{
    return s.replace(/</g, "&lt;")
            .replace(/>/g, "&gt;")
            .replace(/&/g, "&amp;")
            .replace(/"/g, "&quot;")
            .replace(/'/g, "&#39;");
}
```