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
# <a name="creating-and-deploying-policies-for-new-message-types"></a><span data-ttu-id="864a2-102">创建和部署策略的新消息类型</span><span class="sxs-lookup"><span data-stu-id="864a2-102">Creating and Deploying Policies for New Message Types</span></span>
<span data-ttu-id="864a2-103">若要创建和部署策略的新消息类型：</span><span class="sxs-lookup"><span data-stu-id="864a2-103">To create and deploy policies for new message types:</span></span>  
  
1.  <span data-ttu-id="864a2-104">MX 消息文件夹内的消息类型的名称创建一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="864a2-104">Create a folder with the name of the message type inside MX Messages folder.</span></span> <span data-ttu-id="864a2-105">例如，在这种情况下的文件夹的名称将为 setr.004.001.02。</span><span class="sxs-lookup"><span data-stu-id="864a2-105">For example, in this case the name of the folder would be setr.004.001.02.</span></span>  
  
    ```csharp  
    (<xs:complexType name="Document">  
        <xs:sequence>  
            <xs:element name="setr.004.001.02" type="setr.004.001.02"/>  
        </xs:sequence>  
    </xs:complexType>)  
    ```  
  
2.  <span data-ttu-id="864a2-106">将架构文件 (\*.xsd) 以及生成母版 / 此消息类型，此文件夹中文件的验证策略。</span><span class="sxs-lookup"><span data-stu-id="864a2-106">Place the schema file (\*.xsd) along with the resulting master / validation policy file for this message type in this folder.</span></span>  
  
3.  <span data-ttu-id="864a2-107">更新关键字名称 MXMessageTypeKeywordList.xml (C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools)。</span><span class="sxs-lookup"><span data-stu-id="864a2-107">Update the MXMessageTypeKeywordList.xml (C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools) with a keyword name.</span></span> <span data-ttu-id="864a2-108">此名称必须是消息文件夹名称的前四个字母。</span><span class="sxs-lookup"><span data-stu-id="864a2-108">This name must be the first four letters of the message folder name.</span></span> <span data-ttu-id="864a2-109">例如，</span><span class="sxs-lookup"><span data-stu-id="864a2-109">For example,</span></span>  
  
    ```csharp  
    (<Keyword name ="setr" />)  
    ```  
  
4.  <span data-ttu-id="864a2-110">若要创建特定主机 / 验证策略执行的主副本 / 验证策略文件的现有消息，并将其放在新消息文件夹中。</span><span class="sxs-lookup"><span data-stu-id="864a2-110">To create specific master / validation policies, take a copy of the master / validation policy files of the existing message and place it in the new message folder.</span></span>  
  
5.  <span data-ttu-id="864a2-111">更改所有的对 master 数据库中的消息类型的引用 / 验证策略，以便反映新的消息类型。</span><span class="sxs-lookup"><span data-stu-id="864a2-111">Change all of the references to message types in the master / validation policy to reflect the new message types.</span></span>  
  
## <a name="message-naming-conventions"></a><span data-ttu-id="864a2-112">消息命名约定</span><span class="sxs-lookup"><span data-stu-id="864a2-112">Message Naming Conventions</span></span>  
 <span data-ttu-id="864a2-113">遵循这些约定的消息名称：</span><span class="sxs-lookup"><span data-stu-id="864a2-113">Follow these conventions for message names:</span></span>  
  
-   <span data-ttu-id="864a2-114">**替换为消息名称**:如果新消息名称 swift.if.ia.setr.004.001.02 且已使用的策略文件的旧消息 pacs.002.001.02，然后将所有 pacs.002.001.02 的匹配项的替换为 swift.if.ia.setr.004.001.02 策略文件中。</span><span class="sxs-lookup"><span data-stu-id="864a2-114">**Replacing the message name**: If the new message name is swift.if.ia.setr.004.001.02 and the old message whose policy files have been used is pacs.002.001.02, then replace all of the occurrences of pacs.002.001.02 with swift.if.ia.setr.004.001.02 within the policy files.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="864a2-115">消息名称是已下载的架构文件的名称和消息类型是在消息中的文档类型的名称。</span><span class="sxs-lookup"><span data-stu-id="864a2-115">Message name is the name of the schema file which has been downloaded and message type is the name of the document type in the message.</span></span>  
  
-   <span data-ttu-id="864a2-116">保留的消息架构本身相同的策略文件的名称。</span><span class="sxs-lookup"><span data-stu-id="864a2-116">Keep the name of the policy files the same as the message schema itself.</span></span> <span data-ttu-id="864a2-117">例如，swift.if.ia.setr.004.001.02.xsd 将具有以下策略 swift.if.ia.setr.004.001.02 _Master_Policy.xml 和 swift.if.ia.setr.004.001.02 _Validation_Policy.xml。</span><span class="sxs-lookup"><span data-stu-id="864a2-117">For example, swift.if.ia.setr.004.001.02.xsd will have following policies swift.if.ia.setr.004.001.02 _Master_Policy.xml and swift.if.ia.setr.004.001.02 _Validation_Policy.xml.</span></span>  
  
-   <span data-ttu-id="864a2-118">**特殊字符**:如果消息名称中包含任何特殊字符，然后创建的策略文件需要稍有不同的约定。</span><span class="sxs-lookup"><span data-stu-id="864a2-118">**Special characters**: If the message name has any special characters in it, then creating a policy file requires a slightly different convention.</span></span> <span data-ttu-id="864a2-119">如果消息名称，例如，swift.if.ia$setr.004.001.02，则必须更改的策略文件的名称为消息名称包含特殊字符替换为"。"</span><span class="sxs-lookup"><span data-stu-id="864a2-119">If the message name is, for example, swift.if.ia$setr.004.001.02, then you must change the name of the policy file to the message name with the special characters being replaced by “.”</span></span> <span data-ttu-id="864a2-120">例如，如果消息架构文件的名称为 swift.if.ia$setr.004.001.02.xsd，则生成的主策略应 swift.if.ia.setr.004.001.02_Master_Policy.xml。</span><span class="sxs-lookup"><span data-stu-id="864a2-120">For example, if the name of the message schema file is swift.if.ia$setr.004.001.02.xsd, then the resulting master policy would be swift.if.ia.setr.004.001.02_Master_Policy.xml.</span></span>  
  
     <span data-ttu-id="864a2-121">主策略文件也需要更改以反映新的名称在下列标记：</span><span class="sxs-lookup"><span data-stu-id="864a2-121">The master policy file also needs to be changed to reflect the new name in the following tags:</span></span>  
  
    -   <span data-ttu-id="864a2-122">\<ruleset name="swift.if.ia.setr.004.001.02_Master_Policy"\></span><span class="sxs-lookup"><span data-stu-id="864a2-122">\<ruleset name="swift.if.ia.setr.004.001.02_Master_Policy"\></span></span>  
  
    -   <span data-ttu-id="864a2-123"><rule name="swift.if.ia.setr.004.001.02_Policy_List"</span><span class="sxs-lookup"><span data-stu-id="864a2-123"><rule name="swift.if.ia.setr.004.001.02_Policy_List"</span></span>