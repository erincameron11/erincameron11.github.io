---
title: 'Paramedic Incident Data'
date: 2021-01-10
permalink: /posts/2021/01/tps-dispatch-times/
tags:
  - paramedic
  - healthcare
  - public health
---

## *** UNDER CONSTRUCTION ***

An examination of Toronto Paramedic Services' dispatch and incident data found on [The City of Toronto's Open Dataset site](https://open.toronto.ca/dataset/paramedic-services-incident-data/ "Toronto Open Data")


## Section 1
{::options parse_block_html="true" /}

<details open><summary markdown="span">1.0 Loading and cleaning data</summary>

```python
# !{sys.executable} -m pip install requests
# !{sys.executable} -m pip install pandas
# !{sys.executable} -m pip install xlrd
# !{sys.executable} -m pip install openpyxl
# !{sys.executable} -m pip install matplotlib
import sys
import pandas as pd
import requests
import matplotlib.pyplot as plt

dispatches = pd.read_excel(r'/Users/erincameron/Desktop/datacamp/github/datacamp/datasets/tps_incident_data_2010-2019.xlsx')
dispatches.head()
```
</details>
<br/>

{::options parse_block_html="false" /}

