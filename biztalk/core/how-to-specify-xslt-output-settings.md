---
title: 如何指定 XSLT 输出设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c541432-fd4e-41cc-8bcc-f570ce5df439
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1aa3eea4c3f2f4696d3dc1fdf8109aeddec3ff8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255333"
---
# <a name="set-map-compilation-and-output-settings"></a>设置地图编译和输出设置
在 BizTalk 映射程序中设置的映射属性。 

使用这些映射属性后，你可以设置地图的编译方式，包括或排除 XML 声明，以及设置的编码。 

本主题演示如何在你的代码图上设置这些属性。

## <a name="set-the-map-level-compilation"></a>设置地图级别编译

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，你选择`XslTransform`或`XslCompiledTransform`类来编译你的映射。 

1. 在网格视图中打开你的代码图。
2. 在映射器网格中，右键单击任意位置，然后选择**属性**。  
3. 设置**使用 XSL 转换**属性： 

    | 选项 | Description |
    | --- | --- |
    | 未定义 | 使用 XslTransform 设置的注册表标志： <ul><li>64 位主机实例：`HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</li><li>32 位主机实例和 Visual Studio 的测试映射功能：`HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</li></ul> | 
    | True | 映射级别编译属性设置为`XslTransform`（旧行为） | 
    | False | 映射级别编译属性设置为`XslCompiledTransform` | 

> [!NOTE] 
> 从 BizTalk Server 2013 开始，映射器编译行为已更改从`XslTransform`到`XslCompiledTransform`。 [而言有什么映射器更新为你](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/)博客文章提供了相关的行为，并其潜在影响的极佳说明。 
> 
> 从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，您可以选择要编译你的映射的类。 
  
## <a name="include-or-exclude-an-xml-declaration"></a>包括或排除 XML 声明  
你可以选择指示 XML 声明是否为输出。 

1. 在网格视图中打开你的代码图。
2. 在映射器网格中，右键单击任意位置，然后选择**属性**。  
3. 中的下拉列表**省略 XML 声明**属性中，选择**是**省略 XML 声明。 选择**否**无法省略 XML 声明。  

将显示 XML 声明 (如果你选择**否**) 类似于以下。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
```  
  
## <a name="set-encoding-for-output-instance-data"></a>设置编码输出实例数据  
编码为运行时引擎提供确定在创建映射的输出结果时使用的字符集所需的信息。  
   
1. 在网格视图中打开你的代码图。
2. 在映射器网格中，右键单击任意位置，然后选择**属性**。    
3.  中的下拉列表**XSLT 编码**属性，选择你的字符集想用于输出实例数据。  
  
## <a name="see-also"></a>另请参阅  
 [编译和测试映射](../core/compiling-and-testing-maps.md)   
 [使用 BizTalk 映射程序](../core/using-biztalk-mapper.md)   
 [编码类型的有效 BizTalk 映射程序 XSLT](../core/valid-biztalk-mapper-xslt-encoding-types.md)