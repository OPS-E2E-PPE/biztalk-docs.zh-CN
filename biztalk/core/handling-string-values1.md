---
title: 处理字符串 Values1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, configuring strings
- strings, left-justified
- strings, configuring
- strings, right-justified
ms.assetid: a180b818-1009-45f5-a503-d10ed7dd27fc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51397965a416169c8f71ffef8d9466f99f30c093
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988910"
---
# <a name="handling-string-values"></a>处理字符串值
本主题介绍如何将某些字符串参数配置为右对齐（并向左填充）。  
  
## <a name="types-of-string-values"></a>字符串值的类型  
 JD Edwards OneWorld 通过互操作性层显示两种字符串值：  
  
- 单个字符的字符：  
  
- 最大长度字符串  
  
  JD Edwards OneWorld 使用匈牙利符号命名业务函数中这些类型的参数。 例如，这些类型的参数以下列字符开头：  
  
- c  
  
- sz  
  
### <a name="left-justified-values"></a>左对齐值  
 对于大多数的 sz 类型参数，最大长度的字符串或字符数组，JD Edwards OneWorld 应该为左对齐值。 对于街道地址行，最大长度为 40，JD Edwards OneWorld 最好为（示例）：  
  
 "4567 Main St."  
  
 使用空白填充到长度 40。 您无需输入填充，因为 JD Edwards OneWorld 的 Microsoft BizTalk 适配器将为您提供填充内容。 您只需要在客户端代码中输入“4567 Main St.”。  
  
### <a name="right-justified-values"></a>右对齐值  
 对于此类型的某些子集值，JD Edwards OneWorld 预期值右对齐，左边填充。 例如，对于 B4200310 源模块中的业务函数，参数 szBusinessUnit 是长度为 12。 此参数表示工厂，例如生产设施。 为 30，J.D.工厂数 Edwards OneWorld XE 预期值：  
  
 "          30"  
  
 若要输入一个值，将为右对齐，必须在称为 jdearglist.txt 文件中输入参数。 生成架构时将读取 jdearglist.txt。 此文本文件中列出的任何值都会自动转化为右对齐的值，并且填充在左边空白区域。  
  
 必须创建 jdearglist.txt 使用文本编辑器中，具有条目描述这些参数，并将其保存在以下文件夹中： %BizTalk_Install_Adapter%\config\JDE\  
  
 其中 **%biztalk_install_adapter%** 是适用于 JD Edwards OneWorld 安装 BizTalk 适配器的目录。  
  
 如果此文件不存在或为空，当适配器首次打开时，信息性消息将出现在 JD Edwards OneWorld 的 BizTalk 适配器日志中。  
  
> [!NOTE]
>  如果您在生成架构后更改此文件，则必须重新生成架构以刷新其包含的数据。  
  
 要验证您使用的是否是此文件中的最新信息，您可以在重新生成架构之前，使用任务管理器停止 browsingagent.exe 进程；但是，此操作不是必需的。  
  
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
>  当将 JD Edwards OneWorld 业务进程导入到另一台计算机中时，您必须手动复制 jdearglist.txt。  
  
## <a name="see-also"></a>请参阅  
 [在 Jdearglist 中设置字符串对齐](../core/setting-string-justification-in-jdearglist.md)   
 [附录 A：数据类型](../core/appendix-a-data-types.md)