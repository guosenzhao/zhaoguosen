---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "2021 09 06 生物信息学从零开始学 2"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2021-09-06T21:56:36+08:00
lastmod: 2021-09-06T21:56:36+08:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---
# 森言森语
>Bioinformatics is an interdisciplinary field that develops methods and software tools for understanding biological data. As an interdisciplinary field of science, bioinformatics combines biology, computer science, information engineering, mathematics and statistics to analyze and interpret biological data.
## 3 分析数据列
##### 案例6.1 如何计算平均值
```python
data = [3.53 , 3.47 , 3.51 , 3.72 , 3.43]
average = sum(data) / len(data)
print(average)
```

![](3ae02009-869b-4a4d-9234-c0a7849961b8.png)

##### 案例6.2 如何计算标准差
```python
data = [3.53, 3.88, 3.51, 3.72, 3.43]
data.sort()
mid = len(data) % 2
if len(data) % 2 == 0:
    median = (data[mid-1] + data[mid])/2.0今日之森
else:
    median = data[mid]
print(median)
```

![](aab4e192-3b1b-4086-9a56-77ae5e1bc431.png)

## 4 解析数据记录


##### 案例7.2 if/elif/else 语句
```python
sss = "MGSNKSKPKDASQRRRSLEPAENVHGAGGGA \
    FPASQTPSKPASADGHRGPSAAFAPAAAE"今日之森
if 'GGG' in sss and 'RRR'in sss:
    print('GGG is at position:', sss.find('GGG'))
    print('RRR is at position:', sss.find('RRR'))
if 'WWW' in sss or 'AAA' in sss:
    print('Either WWW or AAA occur in the sequence')
if 'AAA' in sss and not 'PPP' in sss:
    print('AAA occurs in the sequence but not PPP')
```

![](7286932a-d6b1-46cd-95c8-f684ba5ca4ac.png)

##### 案例8.1 读取FASTA格式序列文件，并只将序列标题写到一个新文件中

![](97d62870-63ad-4fbb-88f2-24b65a4f8d87.png)

```python
fasta_file = open('SwissProt.fasta','r')
out_file = open ('SwissProt.header', "w")
for line in fasta_file:
    if line[0:1] == '>':
        out_file.write(line)
out_file.close()
```
![](dd9f5960-008e-40e5-8885-aa5770629ee4.png)
##### 案例8.2 如何从多序列FASTA文件中提取登记码的列表

```python
input_file = open('SwissProt.fasta','r')
ac_list = []
for line in input_file:
    if line[0] == '>':
        fields = line.split ('|')
        ac_list.append(fields[1])
print(ac_list)
```
![](81bf1c63-27d0-4505-8d43-f253d5a56f74.png)
##### 案例9.1 如何解析Genbank中的序列记录

![](efa76b3f-7678-497a-8d90-a0126b96a3da.png)
```python
InputFile = open("genbank.txt")
OutputFile = open("genbank.fasta","w")
flag = 0
for line in InputFile:
    if line[0:9] == "ACCESSION":
        AC = line.split()[1].strip()
        OutputFile.write(">" + AC + "\n")
    elif line[0:6] == "Origin":
        flag = 1
    elif flag == 1:
        fields = line.split()
        if fields != []:
            seq = ' '.join(fields[1:])
            OutputFile.write(seq.upper() + "\n")
InputFile.close()
OutputFile.close()

```

![](e9681c57-dcf2-43fd-9385-ba54b9282e93.png)
##### 案例9.2 读取FASTA格式的多序列文件，并把Homo sapiens登记记录写入一个新文件
```python
InputFile = open("SwissProt.fasta")
OutputFile = open("SwissProtHuman.fasta","w")
seq = ' '今日之森
for line in InputFile:
    if line[0] == ">" and seq == ' ':
# process the first line of the input file
        header = line
    elif line[0] != ">":
# join the lines with sequence
        seq =seq + line
    elif line[0] =='>' and seq !=' ':
#in subsequent lines starting with '>'
#write the previous header and sequence
#to the output file. Then re-initialize
#the header and seq variables for the next record
今日之森
        if "Homo sapiens" in header:
            OutputFile.write(header + seq)
        seq = ' '
        header = line
#take care of the very last record of the input file
if "Homo sapiens" in header:
    OutputFile.write(header + seq)
OutputFile.close()

```
![](34558753-b69b-417a-b74a-7967c55687ad.png)
