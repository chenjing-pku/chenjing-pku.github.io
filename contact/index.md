---
title: Contact
nav:
  order: 5
  tooltip: Email, address, and location
---

# {% include icon.html icon="fa-regular fa-envelope" %}Contact

北京市海淀区颐和园路5号(5 yiheyuan road, haidian district, Beijing)\\
北京大学 (Peking University), 100871\\
北京大学理科2号楼2228室(Room 2228, Science Building #2)

{%
  include button.html
  type="email"
  text="janechenjing@pku.edu.cn"
  link="janechenjing@pku.edu.cn"
%}
{%
  include button.html
  type="phone"
  text="86-10-62756824"
  link="86-10-62756824"
%}
{%
  include button.html
  type="personal page"
  text="personal page"
  link="https://sai.pku.edu.cn/info/1362/2249.htm"
%}

{% include section.html %}

{% capture col1 %}

{%
  include figure.html
  image="images/photo.jpg"
  caption="北京大学机器感知与智能教育部重点实验室"
%}

{% endcapture %}

{% capture col2 %}

{%
  include figure.html
  image="images/photo.jpg"
  caption="北京大学智能学院"
%}

{% endcapture %}

{% include cols.html col1=col1 col2=col2 %}

