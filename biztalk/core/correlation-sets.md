---
title: 相关集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, inspecting
- correlation sets, about correlation sets
- correlation sets, passing as parameters
- messages, correlation sets
- correlation sets
- correlation sets, following correlation sets
- correlation sets, initializing
ms.assetid: 528dcd6c-d364-4bb8-8deb-cd4a0791867f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1767755e240171431b01d5997691b800fdbdaa3b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354389"
---
# <a name="correlation-sets"></a>相关集
可以通过定义相关集来实现此的类消息与业务流程实例相关。 相关集是一组属性*具有特定值*。 这是不同于相关类型，即只需的属性列表。 如果传入消息不具有所有这些属性，具有匹配的每个值，则相关将失败并且业务流程实例将不接收此消息。  
  
 相关类型定义一组属性的关联消息。 这些可以是任何属性，之前的属性架构中定义并部署与某个 BizTalk 项目，包括与作为基础 BizTalk 安装的一部分安装的 GlobalPropertySchemas 一起部署的"系统"属性。 相关集定义一组属性和消息必须包含由特定业务流程处理这些属性的值。  
  
 例如，相关类型可能包含以下属性：  
  
|相关类型属性|可能的 XML 表示形式|  
|-------------------------------|---------------------------------|  
|社会保障号|\<SSN\>\</SSN\>|  
|出生日期|\<DOB\>\</DOB\>|  
|性别|\<性别\> \< /性别\>|  
  
 而从该相关类型派生的相关集可由以下属性和值构成：  
  
|相关集属性/值|可能的 XML 表示形式|  
|-------------------------------------|---------------------------------|  
|社会保障号 = 222112222|\<SSN\>222112222\</SSN\>|  
|出生日期 ="1/1/1995"|\<DOB\>”1/1/1995”\</DOB\>|  
|性别 = Male|\<性别\>M \< /性别\>|  
  
> [!NOTE]
>  每个相关集可支持最多三个参数。  
  
## <a name="initializing-correlation-sets"></a>初始化相关集  
  
-   **在接收操作上初始化的相关集**  
  
     在操作定义必须存在的属性组中发布的消息，以使其处理由相应的接收初始化的相关集接收业务流程中操作。 初始化相关集将创建一个相关集，从基于文档中的相应值的相关类型。  
  
-   **在发送操作上初始化的相关集**  
  
     在发送操作上初始化的相关集，从相关类型基于文档中的相应值创建，并且升级出站文档中的相关属性。  
  
## <a name="following-correlation-sets"></a>沿用相关集  
 沿用相关集只能绑定到非激活接收操作或发送操作。 沿用相关集与以前初始化的相关集一前一后指定。  
  
-   **绑定到接收操作的沿用相关集**  
  
     沿用相关集绑定到接收操作定义属性和文档必须包含要接收的值的集。  接收操作的沿用相关集接受包含来自以前初始化的相关集属性的文档。  
  
-   **绑定到发送操作的沿用相关集**  
  
     沿用相关集绑定到发送操作的规定，出站文档中升级中的相关集的属性集。  
  
## <a name="inspecting-correlation-sets"></a>检查相关集  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供检查相关集的能力。 可以使用类似于下面的代码表达式形状中的相关集来检查：  
  
```  
MsgLen = Correlation_1(BTS.MessageLength);  
```  
  
 上面的示例假定已创建一个名为变量**MsgLen**类型的**System.Int16** ，并且您的业务流程中包含一个相关集**Correlation_1**. 若要检查相关集的功能可能需要检查已传递到另一个业务流程通过业务流程的相关值的情况下很有用。  
  
## <a name="passing-correlation-sets-as-parameters-to-orchestrations"></a>向业务流程传递相关集作为参数  
 可以将传递为相关性*在*其他业务流程的参数。