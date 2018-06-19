---
title: 创建架构项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67e6278c-a597-4700-80bf-48e37aaa9c05
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58017b24f7b7464745f48cc202734217dfb327d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207205"
---
# <a name="creating-a-schema-project"></a><span data-ttu-id="96c21-102">创建架构项目</span><span class="sxs-lookup"><span data-stu-id="96c21-102">Creating a Schema Project</span></span>
<span data-ttu-id="96c21-103">若要创建架构项目：</span><span class="sxs-lookup"><span data-stu-id="96c21-103">To create a schema project:</span></span>  
  
1.  <span data-ttu-id="96c21-104">在 Visual Studio 中，创建 SWIFT MX 架构 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="96c21-104">In Visual Studio, create the SWIFT MX Schema BizTalk project.</span></span>  
  
2.  <span data-ttu-id="96c21-105">将相应 MX 架构 （从 ISO20022 站点下载），您想要测试，添加到此项目。</span><span class="sxs-lookup"><span data-stu-id="96c21-105">Add the appropriate MX schema (downloaded from ISO20022 site), which you wish to test, to this project.</span></span>  
  
3.  <span data-ttu-id="96c21-106">如果你想要执行的消息修复功能和新提交功能对于上面的 MX 消息，则还与上面的消息类型相对应的信封架构必须将其部署其他继续执行步骤 6。</span><span class="sxs-lookup"><span data-stu-id="96c21-106">If you want to execute the Message Repair and New Submission functionality for the above MX message, then an Envelope schema corresponding to the above message type also needs to be deployed else proceed to step 6.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96c21-107">有关如何生成 MX 信封架构的信息，请参阅窗体生成器文档。</span><span class="sxs-lookup"><span data-stu-id="96c21-107">For information on how to generate MX Envelope schemas, please refer to the Form Generator Documentation.</span></span>  
  
4.  <span data-ttu-id="96c21-108">将信封架构添加到 SWIFT MX 架构项目。</span><span class="sxs-lookup"><span data-stu-id="96c21-108">Add the Envelope schema to the SWIFT MX Schema project.</span></span>  
  
5.  <span data-ttu-id="96c21-109">在 BizTalk 编辑器中打开信封架构并将提升"CorrelationToken"和"IsNewSubmission"属性。</span><span class="sxs-lookup"><span data-stu-id="96c21-109">Open the Envelope schema in the BizTalk editor and promote “CorrelationToken” and “IsNewSubmission” properties.</span></span> <span data-ttu-id="96c21-110">右键单击上面的字段，然后单击**Promote-> 快速升级**来升级这些属性。</span><span class="sxs-lookup"><span data-stu-id="96c21-110">Right-click the above fields and click **Promote -> Quick Promotion** to promote these properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96c21-111">有关如何升级的架构中的属性的详细信息，请参阅 BizTalk Server 文档。</span><span class="sxs-lookup"><span data-stu-id="96c21-111">For more information on how to promote properties of a schema, please refer to the BizTalk Server documentation.</span></span>  
  
6.  <span data-ttu-id="96c21-112">创建密钥文件 （使用 Sn-k key.snk），然后将其分配给项目以创建强名称程序集。</span><span class="sxs-lookup"><span data-stu-id="96c21-112">Create a key file (using Sn –k key.snk), and then assign it to the project to create a strong named assembly.</span></span>  
  
7.  <span data-ttu-id="96c21-113">生成然后部署项目。</span><span class="sxs-lookup"><span data-stu-id="96c21-113">Build and then deploy the project.</span></span>