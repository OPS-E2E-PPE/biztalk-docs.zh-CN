---
title: "关联集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09bad0bf41f5b509f9a64e9484cac84f66a84e4b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="correlation-sets"></a>关联集
您可以通过定义相关集，实现消息与业务流程实例的此类相关。 相关集是一组属性*具有特定值*。 相关集不同于相关类型，后者只是属性的列表。 如果某一传入消息不具有所有这些属性（每个属性都有匹配的值），则相关将失败，并且业务流程实例将不会收到该消息。  
  
 相关类型定义将关联消息的一组属性。 这些属性可以是以前在属性架构中定义并与某个 BizTalk 项目一起部署的任何属性，包括与作为基础 BizTalk 安装的一部分安装的 GlobalPropertySchemas 一起部署的“system”属性。 相关集对消息必须包含的属性定义一组属性和相应的值，以便特定业务流程对该消息进行处理。  
  
 例如，某一相关类型可由以下属性构成：  
  
|相关类型属性|可能的 XML 表示形式|  
|-------------------------------|---------------------------------|  
|社会保障号|\<SSN\>\</SSN\>|  
|出生日期|\<DOB\>\</DOB\>|  
|性别|\<性别\> \< /性别\>|  
  
 在从该相关类型派生的相关集可由以下属性和值构成时：  
  
|相关集属性/值|可能的 XML 表示形式|  
|-------------------------------------|---------------------------------|  
|社会保障号 = 222112222|\<SSN\>222112222\</SSN\>|  
|出生日期 = “1/1/1995”|\<DOB\>"1/1/1995"\</DOB\>|  
|性别 = Male|\<性别\>M \< /性别\>|  
  
> [!NOTE]
>  每个相关集都支持最多三个字符。  
  
## <a name="initializing-correlation-sets"></a>初始化相关集  
  
-   **关联集上的接收操作的初始化**  
  
     在接收操作上初始化的相关集定义必须在发布的消息中存在的完全匹配的一组属性，以便发布的消息可由业务流程中的相应接收操作进行处理。 初始化相关集将基于某一文档中的相应值，从相关类型创建一个相关集。  
  
-   **关联集初始化发送操作**  
  
     在发送操作上初始化的相关集基于文档中的相应值从某一相关类型创建，并且升级出站文档中的相关属性。  
  
## <a name="following-correlation-sets"></a>沿用相关集  
 沿用相关集只能绑定到非激活接收操作或发送操作。 沿用相关集与以前初始化的相关集一前一后指定。  
  
-   **以下相关集绑定到接收操作**  
  
     绑定到接收操作的沿用相关集定义文档必须包含以便接收的一组属性和值。  具有沿用相关集的接收操作接受包含来自以前初始化的相关集的属性的文档。  
  
-   **以下相关集绑定到的发送操作**  
  
     绑定到发送操作的沿用相关集规定在出站文档中升级相关集中的属性组。  
  
## <a name="inspecting-correlation-sets"></a>检查相关集  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供用于检查关联集。 您可以使用如下代码检查表达式形状中的相关集：  
  
```  
MsgLen = Correlation_1(BTS.MessageLength);  
```  
  
 上面的示例假设你已创建一个名为变量**MsgLen**类型的**System.Int16** ，并且您的业务流程中包含相关设置命名**Correlation_1**. 如果您需要检查已由其他业务流程传递到某一业务流程的相关的值，则能够检查相关集可能就会很有用。  
  
## <a name="passing-correlation-sets-as-parameters-to-orchestrations"></a>将相关集作为参数传递到业务流程  
 你可以将传递作为相关性*中*向其他业务流程的参数。