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
# <a name="creating-and-deploying-policies-for-new-message-types"></a><span data-ttu-id="82597-102">创建和部署新的消息类型的策略</span><span class="sxs-lookup"><span data-stu-id="82597-102">Creating and Deploying Policies for New Message Types</span></span>
<span data-ttu-id="82597-103">若要创建和部署新的消息类型的策略：</span><span class="sxs-lookup"><span data-stu-id="82597-103">To create and deploy policies for new message types:</span></span>  
  
1.  <span data-ttu-id="82597-104">替换 MX 消息文件夹中的消息类型的名称创建一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="82597-104">Create a folder with the name of the message type inside MX Messages folder.</span></span> <span data-ttu-id="82597-105">例如，在这种情况下文件夹的名称将 setr.004.001.02。</span><span class="sxs-lookup"><span data-stu-id="82597-105">For example, in this case the name of the folder would be setr.004.001.02.</span></span>  
  
    ```csharp  
    (<xs:complexType name="Document">  
        <xs:sequence>  
            <xs:element name="setr.004.001.02" type="setr.004.001.02"/>  
        </xs:sequence>  
    </xs:complexType>)  
    ```  
  
2.  <span data-ttu-id="82597-106">将架构文件 (*.xsd) 以及生成母版 / 验证策略文件的此文件夹中的此消息类型。</span><span class="sxs-lookup"><span data-stu-id="82597-106">Place the schema file (*.xsd) along with the resulting master / validation policy file for this message type in this folder.</span></span>  
  
3.  <span data-ttu-id="82597-107">更新关键字名称 MXMessageTypeKeywordList.xml (C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools)。</span><span class="sxs-lookup"><span data-stu-id="82597-107">Update the MXMessageTypeKeywordList.xml (C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools) with a keyword name.</span></span> <span data-ttu-id="82597-108">此名称必须是消息文件夹名称的前四个字母。</span><span class="sxs-lookup"><span data-stu-id="82597-108">This name must be the first four letters of the message folder name.</span></span> <span data-ttu-id="82597-109">例如：</span><span class="sxs-lookup"><span data-stu-id="82597-109">For example,</span></span>  
  
    ```csharp  
    (<Keyword name ="setr" />)  
    ```  
  
4.  <span data-ttu-id="82597-110">若要创建特定母版 / 验证策略会的主副本 / 验证策略文件的现有消息，并将其放入新的消息文件夹。</span><span class="sxs-lookup"><span data-stu-id="82597-110">To create specific master / validation policies, take a copy of the master / validation policy files of the existing message and place it in the new message folder.</span></span>  
  
5.  <span data-ttu-id="82597-111">更改所有对母版中的消息类型的引用 / 验证策略，以反映新的消息类型。</span><span class="sxs-lookup"><span data-stu-id="82597-111">Change all of the references to message types in the master / validation policy to reflect the new message types.</span></span>  
  
## <a name="message-naming-conventions"></a><span data-ttu-id="82597-112">消息的命名约定</span><span class="sxs-lookup"><span data-stu-id="82597-112">Message Naming Conventions</span></span>  
 <span data-ttu-id="82597-113">遵循消息名称以下约定：</span><span class="sxs-lookup"><span data-stu-id="82597-113">Follow these conventions for message names:</span></span>  
  
-   <span data-ttu-id="82597-114">**替换消息名称**： 如果新消息名称 swift.if.ia.setr.004.001.02 且已使用其策略文件的旧消息是 pacs.002.001.02，然后替换所有出现的与 pacs.002.001.02swift.if.ia.setr.004.001.02 的策略文件内。</span><span class="sxs-lookup"><span data-stu-id="82597-114">**Replacing the message name**: If the new message name is swift.if.ia.setr.004.001.02 and the old message whose policy files have been used is pacs.002.001.02, then replace all of the occurrences of pacs.002.001.02 with swift.if.ia.setr.004.001.02 within the policy files.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82597-115">消息名称是已下载的架构文件的名称和消息类型是在消息中的文档类型的名称。</span><span class="sxs-lookup"><span data-stu-id="82597-115">Message name is the name of the schema file which has been downloaded and message type is the name of the document type in the message.</span></span>  
  
-   <span data-ttu-id="82597-116">请使用与消息架构本身相同的策略文件的名称。</span><span class="sxs-lookup"><span data-stu-id="82597-116">Keep the name of the policy files the same as the message schema itself.</span></span> <span data-ttu-id="82597-117">例如，swift.if.ia.setr.004.001.02.xsd 还将具有以下策略 swift.if.ia.setr.004.001.02 _Master_Policy.xml 和 swift.if.ia.setr.004.001.02 _Validation_Policy.xml。</span><span class="sxs-lookup"><span data-stu-id="82597-117">For example, swift.if.ia.setr.004.001.02.xsd will have following policies swift.if.ia.setr.004.001.02 _Master_Policy.xml and swift.if.ia.setr.004.001.02 _Validation_Policy.xml.</span></span>  
  
-   <span data-ttu-id="82597-118">**特殊字符**： 如果消息名称有任何特殊字符，则创建的策略文件需要略有不同的约定。</span><span class="sxs-lookup"><span data-stu-id="82597-118">**Special characters**: If the message name has any special characters in it, then creating a policy file requires a slightly different convention.</span></span> <span data-ttu-id="82597-119">如果消息名称，例如，swift.if.ia$setr.004.001.02，则必须为消息名称更改策略文件的名称，其中包含被取代的特殊字符"。"</span><span class="sxs-lookup"><span data-stu-id="82597-119">If the message name is, for example, swift.if.ia$setr.004.001.02, then you must change the name of the policy file to the message name with the special characters being replaced by “.”</span></span> <span data-ttu-id="82597-120">例如，如果 swift.if.ia$setr.004.001.02.xsd 消息架构文件的名称，则生成的主策略应 swift.if.ia.setr.004.001.02_Master_Policy.xml。</span><span class="sxs-lookup"><span data-stu-id="82597-120">For example, if the name of the message schema file is swift.if.ia$setr.004.001.02.xsd, then the resulting master policy would be swift.if.ia.setr.004.001.02_Master_Policy.xml.</span></span>  
  
     <span data-ttu-id="82597-121">主策略文件也需要更改以反映新名称出现在以下标记：</span><span class="sxs-lookup"><span data-stu-id="82597-121">The master policy file also needs to be changed to reflect the new name in the following tags:</span></span>  
  
    -   <span data-ttu-id="82597-122">\<ruleset name="swift.if.ia.setr.004.001.02_Master_Policy"\></span><span class="sxs-lookup"><span data-stu-id="82597-122">\<ruleset name="swift.if.ia.setr.004.001.02_Master_Policy"\></span></span>  
  
    -   <span data-ttu-id="82597-123">< 规则 name="swift.if.ia.setr.004.001.02_Policy_List"</span><span class="sxs-lookup"><span data-stu-id="82597-123"><rule name="swift.if.ia.setr.004.001.02_Policy_List"</span></span>