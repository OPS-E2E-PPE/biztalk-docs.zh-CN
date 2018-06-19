---
title: 处理字符串 Values2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- string values, configuring
- formatting strings
- strings, formatting
- left-justified string values
- jdearglist.txt
- strings, left-justified
- right-justified string values
- strings, right-justified
ms.assetid: 23d54731-b2b9-4610-a533-e041237e0bb3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 024663faa56d92361d861a61a0d64a4608839aa6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22246365"
---
# <a name="handling-string-values"></a>处理字符串值
本主题介绍如何将某些字符串参数配置为右对齐（并向左填充）。  
  
## <a name="types-of-string-values"></a>字符串值的类型  
 JD Edwards EnterpriseOne 通过其互操作层公开两种字符串值：  
  
-   char︰ 单个字符  
  
-   最大长度字符串  
  
 JD Edwards EnterpriseOne 使用匈牙利语表示法来命名业务功能中这些类型的参数。 例如，这些类型的参数以下列字符开头：  
  
-   c  
  
-   sz  
  
### <a name="left-justified-values"></a>左对齐值  
 对于大多数 sz 类型的参数、最大长度字符串或字符数组，JD Edwards EnterpriseOne 期望左对齐值。 例如，对于最大长度为 40 的街道地址行，JD Edwards EnterpriseOne 期望（例如）：  
  
 “4567 Main St.    ”  
  
 使用空白填充到长度 40。 您不需要输入填充值，因为 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器为您提供此值。 只需要在您的客户端代码中输入“4567 Main St”。  
  
### <a name="right-justified-values"></a>右对齐值  
 对于此类型的值的一些子集，JD Edwards EnterpriseOne 期望使用左边填充的右对齐值。 例如，对于业务 B4200310 源模块中的函数，参数 szBusinessUnit 是长度为 12。 此自变量表示工厂，例如生产设施。 对于工厂号 30，JD Edwards EnterpriseOne 期望以下列形式表示该值：  
  
 "           30"  
  
 若要输入一个值，将为右对齐，必须在名为 jdearglist.txt 输入参数。 生成架构时读取 jdearglist.txt。 此文本文件中的任何值将自动转换为右对齐值并使用空白填充左边。  
  
 必须使用文本编辑器创建 jdearglist.txt（使用描述这些参数的条目），并将其保存在以下文件夹中：  
  
 C:\Program Files\Microsoft BizTalk Adapters\JDEEnterpriseOne\config  
  
 如果此文件不存在或为空，则在 JD Edwards EnterpriseOne 的 BizTalk 适配器第一次打开时，将在其日志中显示信息消息。  
  
> [!NOTE]
>  如果您在生成架构后更改此文件，则必须重新生成架构以刷新其包含的数据。 要验证您使用的是否是此文件中的最新信息，您可以在重新生成架构之前，使用任务管理器停止 browsingagent.exe 进程；但是，此操作不是必需的。  
  
 以下是 jdearglist.txt 文件中条目格式的示例：  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
  
```  
  
 例如：  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 对于属于同一业务模块的一组业务功能，在某些或所有业务功能中共享 like-named 参数（同一类型）。 您可以使用通配符 (*) 代替业务功能名称。 例如：  
  
```  
B4200310.*.szBusinessUnit  
  
```  
  
> [!NOTE]
>  在将 JD Edwards EnterpriseOne 业务流程导入另一台计算机时，必须手动复制 jdearglist.txt。  
  
## <a name="see-also"></a>另请参阅  
 [附录 B：数据类型](../core/appendix-b-data-types.md)