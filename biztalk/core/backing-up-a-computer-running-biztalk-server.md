---
title: "备份运行 BizTalk Server 的计算机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70f53b41-8083-4b56-8698-e75a13b21a69
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 537ea40b39ecd35127b62f8d96f0175e98a1f3b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-a-computer-running-biztalk-server"></a><span data-ttu-id="c775a-102">对运行 BizTalk Server 的计算机进行备份</span><span class="sxs-lookup"><span data-stu-id="c775a-102">Backing Up a Computer Running BizTalk Server</span></span>
<span data-ttu-id="c775a-103">如果运行 BizTalk Server 的计算机出现了不可恢复的硬件故障，则必须用相同的计算机来替代它。</span><span class="sxs-lookup"><span data-stu-id="c775a-103">If a computer running BizTalk Server suffers an irrecoverable hardware failure, then you must replace that computer with an identical one.</span></span> <span data-ttu-id="c775a-104">您应该在替代计算机上安装基本平台软件、必备软件和 BizTalk Server 组件，并设置相同的配置。</span><span class="sxs-lookup"><span data-stu-id="c775a-104">You should set up the replacement computer with the base platform software, software prerequisites, BizTalk Server components, and identical configuration settings.</span></span> <span data-ttu-id="c775a-105">这些配置设置包括相应的注册表项、文件、文件夹以及正确操作 BizTalk 应用程序所需的相关 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="c775a-105">These configuration settings may consist of the appropriate registry entries, files, folders, and related Windows services necessary for the correct operation of your BizTalk applications.</span></span>  
  
 <span data-ttu-id="c775a-106">为了确保在发生硬件故障后能够恢复 BizTalk Server，除了备份 BizTalk Server 数据库外，还应备份以下 BizTalk Server 组件：</span><span class="sxs-lookup"><span data-stu-id="c775a-106">In addition to backing up the BizTalk Server databases, you should back up the following BizTalk Server components to ensure that you can recover BizTalk Server after a hardware failure:</span></span>  
  
-   <span data-ttu-id="c775a-107">BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="c775a-107">BizTalk Server configuration</span></span>  
  
-   <span data-ttu-id="c775a-108">企业单一登录 (SSO) 主密钥</span><span class="sxs-lookup"><span data-stu-id="c775a-108">Enterprise Single Sign-On (SSO) master secret</span></span>  
  
-   <span data-ttu-id="c775a-109">业务活动监视 (BAM) 门户（不使用 BAM 时不需要）</span><span class="sxs-lookup"><span data-stu-id="c775a-109">Business Activity Monitoring (BAM) portal (not required unless you're using BAM)</span></span>  
  
-   <span data-ttu-id="c775a-110">BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="c775a-110">BizTalk applications</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c775a-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="c775a-111">In This Section</span></span>  
  
-   [<span data-ttu-id="c775a-112">如何备份的 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="c775a-112">How to Back Up The BizTalk Server Configuration</span></span>](../core/how-to-back-up-the-biztalk-server-configuration.md)  
  
-   [<span data-ttu-id="c775a-113">如何备份主密钥</span><span class="sxs-lookup"><span data-stu-id="c775a-113">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  
  
-   [<span data-ttu-id="c775a-114">如何备份 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="c775a-114">How to Back Up the BAM Portal</span></span>](../core/how-to-back-up-the-bam-portal.md)  
  
-   [<span data-ttu-id="c775a-115">备份 BizTalk 服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="c775a-115">Backing Up BizTalk Server Applications</span></span>](../core/backing-up-biztalk-server-applications.md)