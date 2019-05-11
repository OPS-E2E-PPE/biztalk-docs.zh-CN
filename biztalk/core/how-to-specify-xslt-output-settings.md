---
title: 如何指定 XSLT 输出设置 |Microsoft Docs
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
ms.openlocfilehash: a1174466897c94b1a7797c32620e88dae6ae57c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334037"
---
# <a name="set-map-compilation-and-output-settings"></a>设置映射编译和输出设置
在 BizTalk 映射器中设置映射属性。 

使用这些映射属性后，可以设置地图的编译方式，包括或排除 XML 声明，以及设置的编码。 

本主题演示如何对地图上设置这些属性。

## <a name="set-the-map-level-compilation"></a>设置地图级别编译

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，选择`XslTransform`或`XslCompiledTransform`类来编译您的映射。 

1. 在网格视图中打开您的映射。
2. 在映射器网格中，右键单击任意位置，然后选择**属性**。  
3. 设置**使用 XSL 转换**属性： 

    | Option | Description |
    | --- | --- |
    | 未定义 | 使用 XslTransform 设置的注册表标志： <ul><li>64 位主机实例： `HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</li><li>32 位主机实例和 Visual Studio 的测试映射功能： `HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</li></ul> | 
    | True | 映射级别编译属性设置为`XslTransform`（旧版行为） | 
    | False | 映射级别编译属性设置为 `XslCompiledTransform` | 

> [!NOTE]
> 从 BizTalk Server 2013 开始，映射器编译行为已更改从`XslTransform`到`XslCompiledTransform`。 [什么映射器更新的意义](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/)博客文章提供了很好说明的行为和它的潜在影响。 
> 
> 从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，可以选择要编译映射的类。 
  
## <a name="include-or-exclude-an-xml-declaration"></a>包含或排除的 XML 声明  
您可以选择指示 XML 声明是否为输出。 

1. 在网格视图中打开您的映射。
2. 在映射器网格中，右键单击任意位置，然后选择**属性**。  
3. 中的下拉列表**忽略 XML 声明**属性中，选择**是**省略 XML 声明。 选择**否**不以省略 XML 声明。  

将出现 XML 声明 (如果选择了**否**) 如下所示。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
```  
  
## <a name="set-encoding-for-output-instance-data"></a>设置编码为输出实例数据  
编码提供运行时引擎，它需要用来确定哪一字符集创建映射的输出结果时要使用的信息。  
   
1. 在网格视图中打开您的映射。
2. 在映射器网格中，右键单击任意位置，然后选择**属性**。    
3.  中的下拉列表**XSLT 编码**属性中，选择的字符集想用于输出实例数据。  
  
## <a name="see-also"></a>请参阅  
 [编译和测试映射](../core/compiling-and-testing-maps.md)   
 [使用 BizTalk 映射器](../core/using-biztalk-mapper.md)   
 [有效的 BizTalk 映射器 XSLT 编码类型](../core/valid-biztalk-mapper-xslt-encoding-types.md)