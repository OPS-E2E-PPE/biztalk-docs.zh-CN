---
title: "消息类型创建和部署新的策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43343238-ec45-44ed-a230-9e234bd22d05
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b826b3ee9408caf91fe5adcb2177d709f885a6e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="creating-and-deploying-policies-for-new-message-types"></a>创建和部署新的消息类型的策略
若要创建和部署新的消息类型的策略：  
  
1.  替换 MX 消息文件夹中的消息类型的名称创建一个文件夹。 例如，在这种情况下文件夹的名称将 setr.004.001.02。  
  
    ```csharp  
    (<xs:complexType name="Document">  
        <xs:sequence>  
            <xs:element name="setr.004.001.02" type="setr.004.001.02"/>  
        </xs:sequence>  
    </xs:complexType>)  
    ```  
  
2.  将架构文件 (*.xsd) 以及生成母版 / 验证策略文件的此文件夹中的此消息类型。  
  
3.  更新关键字名称 MXMessageTypeKeywordList.xml (C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools)。 此名称必须是消息文件夹名称的前四个字母。 例如：  
  
    ```csharp  
    (<Keyword name ="setr" />)  
    ```  
  
4.  若要创建特定母版 / 验证策略会的主副本 / 验证策略文件的现有消息，并将其放入新的消息文件夹。  
  
5.  更改所有对母版中的消息类型的引用 / 验证策略，以反映新的消息类型。  
  
## <a name="message-naming-conventions"></a>消息的命名约定  
 遵循消息名称以下约定：  
  
-   **替换消息名称**： 如果新消息名称 swift.if.ia.setr.004.001.02 且已使用其策略文件的旧消息是 pacs.002.001.02，然后替换所有出现的与 pacs.002.001.02swift.if.ia.setr.004.001.02 的策略文件内。  
  
    > [!NOTE]
    >  消息名称是已下载的架构文件的名称和消息类型是在消息中的文档类型的名称。  
  
-   请使用与消息架构本身相同的策略文件的名称。 例如，swift.if.ia.setr.004.001.02.xsd 还将具有以下策略 swift.if.ia.setr.004.001.02 _Master_Policy.xml 和 swift.if.ia.setr.004.001.02 _Validation_Policy.xml。  
  
-   **特殊字符**： 如果消息名称有任何特殊字符，则创建的策略文件需要略有不同的约定。 如果消息名称，例如，swift.if.ia$setr.004.001.02，则必须为消息名称更改策略文件的名称，其中包含被取代的特殊字符"。" 例如，如果 swift.if.ia$setr.004.001.02.xsd 消息架构文件的名称，则生成的主策略应 swift.if.ia.setr.004.001.02_Master_Policy.xml。  
  
     主策略文件也需要更改以反映新名称出现在以下标记：  
  
    -   \<ruleset name="swift.if.ia.setr.004.001.02_Master_Policy"\>  
  
    -   < 规则 name="swift.if.ia.setr.004.001.02_Policy_List"