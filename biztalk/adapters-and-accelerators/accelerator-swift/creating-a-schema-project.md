---
title: 创建架构项目 |Microsoft Docs
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
ms.openlocfilehash: 4a6419c008a95277256c75fbd0b7d6dda388061f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378467"
---
# <a name="creating-a-schema-project"></a><span data-ttu-id="463cd-102">创建架构项目</span><span class="sxs-lookup"><span data-stu-id="463cd-102">Creating a Schema Project</span></span>
<span data-ttu-id="463cd-103">若要创建架构项目：</span><span class="sxs-lookup"><span data-stu-id="463cd-103">To create a schema project:</span></span>  
  
1.  <span data-ttu-id="463cd-104">在 Visual Studio 中，创建 SWIFT MX 架构 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="463cd-104">In Visual Studio, create the SWIFT MX Schema BizTalk project.</span></span>  
  
2.  <span data-ttu-id="463cd-105">将相应 MX 下载的架构 （从 ISO20022 站点），你要测试，添加到此项目。</span><span class="sxs-lookup"><span data-stu-id="463cd-105">Add the appropriate MX schema (downloaded from ISO20022 site), which you wish to test, to this project.</span></span>  
  
3.  <span data-ttu-id="463cd-106">如果你想要执行上述 MX 消息的消息修复和新提交功能然后也与上面的消息类型相对应的信封架构需要部署其他继续执行步骤 6。</span><span class="sxs-lookup"><span data-stu-id="463cd-106">If you want to execute the Message Repair and New Submission functionality for the above MX message, then an Envelope schema corresponding to the above message type also needs to be deployed else proceed to step 6.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="463cd-107">有关如何生成 MX 信封架构的信息，请参阅窗体生成器文档。</span><span class="sxs-lookup"><span data-stu-id="463cd-107">For information on how to generate MX Envelope schemas, please refer to the Form Generator Documentation.</span></span>  
  
4.  <span data-ttu-id="463cd-108">将信封架构添加到 SWIFT MX 架构项目。</span><span class="sxs-lookup"><span data-stu-id="463cd-108">Add the Envelope schema to the SWIFT MX Schema project.</span></span>  
  
5.  <span data-ttu-id="463cd-109">在 BizTalk 编辑器中打开信封架构并将提升"CorrelationToken"和"IsNewSubmission"属性。</span><span class="sxs-lookup"><span data-stu-id="463cd-109">Open the Envelope schema in the BizTalk editor and promote “CorrelationToken” and “IsNewSubmission” properties.</span></span> <span data-ttu-id="463cd-110">右键单击上述字段，然后单击**提升-> 快速升级**以升级这些属性。</span><span class="sxs-lookup"><span data-stu-id="463cd-110">Right-click the above fields and click **Promote -> Quick Promotion** to promote these properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="463cd-111">有关如何升级属性架构的详细信息，请参阅 BizTalk Server 文档。</span><span class="sxs-lookup"><span data-stu-id="463cd-111">For more information on how to promote properties of a schema, please refer to the BizTalk Server documentation.</span></span>  
  
6.  <span data-ttu-id="463cd-112">创建密钥文件 （使用 Sn – k key.snk），并再将其分配给项目创建强名称程序集。</span><span class="sxs-lookup"><span data-stu-id="463cd-112">Create a key file (using Sn –k key.snk), and then assign it to the project to create a strong named assembly.</span></span>  
  
7.  <span data-ttu-id="463cd-113">生成，然后部署该项目。</span><span class="sxs-lookup"><span data-stu-id="463cd-113">Build and then deploy the project.</span></span>