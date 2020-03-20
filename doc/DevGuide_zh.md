# OCP2PCIe
 OCP 夹层网卡转标准 PCIe 槽转接卡设计  
 OCP Mezzanine card V2.0 to standard PCIe slot adapter design
 
 请使用最新版 KiCAD 编辑  
 Please use the latest KiCAD version
 
 KCORES HomeLab 交流群 826702309

# Catalog
**目录**
- **Directory Description**  
 **文件说明**   
 
  - Name Rule  
   项目命名规则  
 
- **Manufacturing instructions**  
**制造说明**

- **Some Problem**  
**疑难问题**

  - About PCIe Lanes Sequence  
   关于 PCIe 通道顺序问题
   
  - ⚠About 5V Power⚠  
   关于5V供电


# Directory Description
**文件说明**  

`\OCP2PCIe_Lib`  
OCP2PCIe 公共 KiCAD 库  
OCP2PCIe public KiCAD lib

`\OCP2PCIe-*-*-*`  
项目分类，命名规则见下一节  
Project classification, see the next section

## Name Rule
 **项目命名规则**  
 
 `OCP2PCIe-H-F-4-V0.1`  @
 
 - OCP2PCIe 项目名称 / Project Name  
 
 - H: 全高 PCI 卡 / Standard Height PCI Card  
 L: 半高 PCI 卡 / Low-Profile PCI Card
 
 - F: PCIe 通道顺序连接 / PCIe lane sequential connection  
 R: PCIe 通道逆序连接 / PCIe lane reverse connection  
 详细描述见最后一节 / See the last paragraph for a detailed explanation
 
 - 1/2/4/8/16: PCIe 通道数 / PCIe Lanes  
 
 - V0.1: 版本号 / Version
 
# Manufacturing instructions
**制造说明**

undone

# Some Problem 
**疑难问题**

## About PCIe Lanes Sequence
**关于 PCIe 通道顺序问题**

OCP卡有两种不同的连接方式，目前已知这两种方式都可以工作，但具体的性能和稳定性影响未知  
OCP Mezz has two different connection methods. Currently it is known that both methods can work, but the specific performance and stability impact is unknown.

- 顺序连接 / Sequential connection  
OCP插槽通道与PCIe通道按顺序相连，如0-0、1-1、2-2、3-3  
The OCP slot lanes are sequentially connected to the PCIe lanes, etc: 0-0, 1-1, 2-2, 3-3  

- 逆序连接 / Reverse link  
OCP插槽通道与PCIe通道按逆序相连，如7-0、6-1、5-2、4-3  
The OCP slot lanes are sequentially connected to the PCIe lanes, etc: 7-0, 6-1, 5-2, 4-3

## About 5V Power
**关于5V供电**

OCP规范需要5V辅助供电，目前已知情况如下：  
 The OCP specification requires a 5V auxiliary power supply. The current known situation is as follows:  

- 不需要5V  
 Don't need 5V
    - intel X540

- 需要5V，但5V电路元器件与12V一致，可以直接与12V连接  
 5V is required, but the 5V circuit components are consistent with 12V and can be directly connected to 12V
    - Mellanox MCX341A  
    - Mellanox MCX342A

- 必须提供稳定的5V供电  
 Must provide stable 5V power
    - 未知 / Uknown

