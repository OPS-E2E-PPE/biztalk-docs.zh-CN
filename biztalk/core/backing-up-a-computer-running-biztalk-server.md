---
title: 备份运行 BizTalk Server 的计算机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70f53b41-8083-4b56-8698-e75a13b21a69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04f8a0073ffd4117da1d5cf5d92dd969b9a0abfc
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528576"
---
# <a name="backing-up-a-computer-running-biztalk-server"></a><span data-ttu-id="484cd-102">备份运行 BizTalk Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="484cd-102">Backing Up a Computer Running BizTalk Server</span></span>
<span data-ttu-id="484cd-103">如果运行 BizTalk Server 的计算机出现了不可恢复的硬件故障，必须将该计算机为使用完全相同。</span><span class="sxs-lookup"><span data-stu-id="484cd-103">If a computer running BizTalk Server suffers an irrecoverable hardware failure, then you must replace that computer with an identical one.</span></span> <span data-ttu-id="484cd-104">应设置基本平台软件、 必备软件、 BizTalk Server 组件和设置相同的配置在替代计算机。</span><span class="sxs-lookup"><span data-stu-id="484cd-104">You should set up the replacement computer with the base platform software, software prerequisites, BizTalk Server components, and identical configuration settings.</span></span> <span data-ttu-id="484cd-105">这些配置设置可能会包含相应的注册表项、 文件、 文件夹和 BizTalk 应用程序正确操作所需的相关的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="484cd-105">These configuration settings may consist of the appropriate registry entries, files, folders, and related Windows services necessary for the correct operation of your BizTalk applications.</span></span>  
  
 <span data-ttu-id="484cd-106">除了备份 BizTalk Server 数据库，您应备份以下 BizTalk Server 组件，以确保可以在硬件故障后恢复 BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="484cd-106">In addition to backing up the BizTalk Server databases, you should back up the following BizTalk Server components to ensure that you can recover BizTalk Server after a hardware failure:</span></span>  
  
-   <span data-ttu-id="484cd-107">BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="484cd-107">BizTalk Server configuration</span></span>  
  
-   <span data-ttu-id="484cd-108">企业单一登录 (SSO) 主密钥</span><span class="sxs-lookup"><span data-stu-id="484cd-108">Enterprise Single Sign-On (SSO) master secret</span></span>  
  
-   <span data-ttu-id="484cd-109">业务活动监视 (BAM) 门户 （除非使用 BAM 时不需要）</span><span class="sxs-lookup"><span data-stu-id="484cd-109">Business Activity Monitoring (BAM) portal (not required unless you're using BAM)</span></span>  
  
-   <span data-ttu-id="484cd-110">BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="484cd-110">BizTalk applications</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="484cd-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="484cd-111">In This Section</span></span>  
  
-   [<span data-ttu-id="484cd-112">如何备份 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="484cd-112">How to Back Up The BizTalk Server Configuration</span></span>](../core/how-to-back-up-the-biztalk-server-configuration.md)  
  
-   [<span data-ttu-id="484cd-113">如何备份主密钥</span><span class="sxs-lookup"><span data-stu-id="484cd-113">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  
  
-   [<span data-ttu-id="484cd-114">如何备份 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="484cd-114">How to Back Up the BAM Portal</span></span>](../core/how-to-back-up-the-bam-portal.md)  
  
-   [<span data-ttu-id="484cd-115">备份 BizTalk Server 应用程序</span><span class="sxs-lookup"><span data-stu-id="484cd-115">Backing Up BizTalk Server Applications</span></span>](../core/backing-up-biztalk-server-applications.md)