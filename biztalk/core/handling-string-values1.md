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
ms.openlocfilehash: 4a86b4b04b481e094efe703190c8da7dd86e0c14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387607"
---
# <a name="handling-string-values"></a>处理字符串值
本主题介绍如何将某些字符串参数配置为右对齐 （并向左填充）。  
  
## <a name="types-of-string-values"></a>字符串值的类型  
 JD Edwards OneWorld 公开两种类型的字符串值，通过其互操作性层：  
  
- 单个字符的字符：  
  
- 最大长度的字符串  
  
  JD Edwards OneWorld 使用匈牙利表示法来命名业务函数中这些类型的参数。 例如，这些类型的参数以开始使用：  
  
- c  
  
- sz  
  
### <a name="left-justified-values"></a>左对齐值  
 对于大多数 sz 类型参数，最大长度字符串或字符数组，JD Edwards OneWorld 期望左对齐值。 街道地址行，其最大长度为 40，JD Edwards OneWorld 期望 （例如）：  
  
 "4567 Main St."  
  
 填充到长度 40 具有空白。 不是你输入填充，因为用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供这为你所必需的。 只需在客户端代码中输入"4567 Main St."。  
  
### <a name="right-justified-values"></a>右对齐值  
 此类型的值的一些子集，JD Edwards OneWorld 预期值右对齐，左边填充。 例如，对于 B4200310 源模块中的业务函数，参数 szBusinessUnit 是长度为 12。 此参数表示工厂，例如生产设施。 为 30，J.D.工厂数 Edwards OneWorld XE 预期值：  
  
 "          30"  
  
 若要输入一个值，将为右对齐，必须在称为 jdearglist.txt 文件中输入参数。 生成架构时将读取 jdearglist.txt。 此文本文件中列出的任何值自动转换为右对齐值并填充在左边空白区域。  
  
 必须创建 jdearglist.txt 使用文本编辑器中，具有条目描述这些参数，并将其保存在以下文件夹中： %BizTalk_Install_Adapter%\config\JDE\  
  
 其中 **%biztalk_install_adapter%** 是适用于 JD Edwards OneWorld 安装 BizTalk 适配器的目录。  
  
 如果此文件不存在或为空，适配器首次打开时在 JD Edwards OneWorld 日志的 BizTalk 适配器将显示一条信息性消息。  
  
> [!NOTE]
>  如果您生成架构后更改此文件，必须重新生成架构以刷新其包含的数据。  
  
 若要验证此文件中使用的最新信息，可以使用任务管理器重新生成架构; 先停止 browsingagent.exe 进程但是，这应不是必要。  
  
 以下是 jdearglist.txt 文件中的条目的格式示例：  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
```  
  
 例如：  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 对于属于同一业务模块的业务功能集，在某些或所有业务功能共享 like-named 参数 （属于同一类型）。 您可以使用通配符 （*） 代替业务功能名称。 例如：  
  
```  
B4200310.*.szBusinessUnit  
```  
  
> [!NOTE]
>  当 JD Edwards OneWorld 业务流程导入另一台计算机，则必须手动复制 jdearglist.txt。  
  
## <a name="see-also"></a>请参阅  
 [在 Jdearglist 中设置字符串对齐](../core/setting-string-justification-in-jdearglist.md)   
 [附录 a:数据类型](../core/appendix-a-data-types.md)