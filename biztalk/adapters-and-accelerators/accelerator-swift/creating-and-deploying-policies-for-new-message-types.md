---
title: 创建和部署策略的新消息类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43343238-ec45-44ed-a230-9e234bd22d05
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 570afc1035b9b9430c7f223df4dcec8b82eab756
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378458"
---
# <a name="creating-and-deploying-policies-for-new-message-types"></a>创建和部署策略的新消息类型
若要创建和部署策略的新消息类型：  
  
1.  MX 消息文件夹内的消息类型的名称创建一个文件夹。 例如，在这种情况下的文件夹的名称将为 setr.004.001.02。  
  
    ```csharp  
    (<xs:complexType name="Document">  
        <xs:sequence>  
            <xs:element name="setr.004.001.02" type="setr.004.001.02"/>  
        </xs:sequence>  
    </xs:complexType>)  
    ```  
  
2.  将架构文件 (*.xsd) 以及生成母版 / 此消息类型，此文件夹中文件的验证策略。  
  
3.  更新关键字名称 MXMessageTypeKeywordList.xml (C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools)。 此名称必须是消息文件夹名称的前四个字母。 例如，  
  
    ```csharp  
    (<Keyword name ="setr" />)  
    ```  
  
4.  若要创建特定主机 / 验证策略执行的主副本 / 验证策略文件的现有消息，并将其放在新消息文件夹中。  
  
5.  更改所有的对 master 数据库中的消息类型的引用 / 验证策略，以便反映新的消息类型。  
  
## <a name="message-naming-conventions"></a>消息命名约定  
 遵循这些约定的消息名称：  
  
-   **替换为消息名称**:如果新消息名称 swift.if.ia.setr.004.001.02 且已使用的策略文件的旧消息 pacs.002.001.02，然后将所有 pacs.002.001.02 的匹配项的替换为 swift.if.ia.setr.004.001.02 策略文件中。  
  
    > [!NOTE]
    >  消息名称是已下载的架构文件的名称和消息类型是在消息中的文档类型的名称。  
  
-   保留的消息架构本身相同的策略文件的名称。 例如，swift.if.ia.setr.004.001.02.xsd 将具有以下策略 swift.if.ia.setr.004.001.02 _Master_Policy.xml 和 swift.if.ia.setr.004.001.02 _Validation_Policy.xml。  
  
-   **特殊字符**:如果消息名称中包含任何特殊字符，然后创建的策略文件需要稍有不同的约定。 如果消息名称，例如，swift.if.ia$setr.004.001.02，则必须更改的策略文件的名称为消息名称包含特殊字符替换为"。" 例如，如果消息架构文件的名称为 swift.if.ia$setr.004.001.02.xsd，则生成的主策略应 swift.if.ia.setr.004.001.02_Master_Policy.xml。  
  
     主策略文件也需要更改以反映新的名称在下列标记：  
  
    -   \<ruleset name="swift.if.ia.setr.004.001.02_Master_Policy"\>  
  
    -   <rule name="swift.if.ia.setr.004.001.02_Policy_List"