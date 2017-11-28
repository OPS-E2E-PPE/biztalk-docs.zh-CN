---
title: "安装 BizTalk 适配器包 2016年 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23c74470-6336-49be-95c3-32b5c279e0ab
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fec17ce2da0183b9029839d3054261c5db3952a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="db803-102">安装 BizTalk 适配器包 2016</span><span class="sxs-lookup"><span data-stu-id="db803-102">Install the BizTalk Adapter Pack 2016</span></span>
## <a name="overview"></a><span data-ttu-id="db803-103">概述</span><span class="sxs-lookup"><span data-stu-id="db803-103">Overview</span></span>

<span data-ttu-id="db803-104">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] (BAP) 是附带[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="db803-104">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] (BAP) is included with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="db803-105">因此，当你下载[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，你还将下载中的适配器[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="db803-105">So when you download [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], you are also downloading the adapters in the [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)].</span></span> 

<span data-ttu-id="db803-106">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]使用[!INCLUDE[firstref_btsWinCommFoundation_md](../includes/firstref-btswincommfoundation-md.md)]与不同企业的业务线 (LOB) 系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="db803-106">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] uses the [!INCLUDE[firstref_btsWinCommFoundation_md](../includes/firstref-btswincommfoundation-md.md)] to communicate with different enterprise line-of-business (LOB) systems.</span></span> <span data-ttu-id="db803-107">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]具有自己的要求、 其自己的安装体验和其自己的安装步骤集。</span><span class="sxs-lookup"><span data-stu-id="db803-107">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] has its own set of requirements, its own setup experience, and its own installation steps.</span></span> 

<span data-ttu-id="db803-108">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]是可选的情况，如果你想仅需[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]发送或接收到任何以下企业 LOB 系统的消息：</span><span class="sxs-lookup"><span data-stu-id="db803-108">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] is optional, and is only needed if you want [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to send or receive messages to any of the following enterprise LOB systems:</span></span> 

* <span data-ttu-id="db803-109">Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="db803-109">Oracle Database</span></span>
* <span data-ttu-id="db803-110">Oracle E-business Suite (EBS)</span><span class="sxs-lookup"><span data-stu-id="db803-110">Oracle E-Business Suite (EBS)</span></span>
* <span data-ttu-id="db803-111">SAP</span><span class="sxs-lookup"><span data-stu-id="db803-111">SAP</span></span>
* <span data-ttu-id="db803-112">SQL Server</span><span class="sxs-lookup"><span data-stu-id="db803-112">SQL Server</span></span>
* <span data-ttu-id="db803-113">Siebel</span><span class="sxs-lookup"><span data-stu-id="db803-113">Siebel</span></span>

<span data-ttu-id="db803-114">每个版本的[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]包括其自己[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]版本。</span><span class="sxs-lookup"><span data-stu-id="db803-114">Every version of [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] includes its own [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] version.</span></span> <span data-ttu-id="db803-115">仅附带的版本你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本受支持。</span><span class="sxs-lookup"><span data-stu-id="db803-115">Only the version included with your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] version is supported.</span></span> <span data-ttu-id="db803-116">它们不是向后兼容。</span><span class="sxs-lookup"><span data-stu-id="db803-116">They are not backward-compatible.</span></span>

<span data-ttu-id="db803-117">本文档列出的软件要求和步骤安装 Microsoft BizTalk 适配器包 (BAP) 中包含[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="db803-117">This document lists the software requirements, and the steps to install the Microsoft BizTalk Adapter Pack (BAP) included with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)].</span></span> 

## <a name="get-started-here"></a><span data-ttu-id="db803-118">从此处开始</span><span class="sxs-lookup"><span data-stu-id="db803-118">Get started here</span></span>
[<span data-ttu-id="db803-119">软件必备项</span><span class="sxs-lookup"><span data-stu-id="db803-119">Software prerequisites</span></span>](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="db803-120">安装步骤</span><span class="sxs-lookup"><span data-stu-id="db803-120">Install steps</span></span>](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="db803-121">安装后步骤</span><span class="sxs-lookup"><span data-stu-id="db803-121">Post installation steps</span></span>](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="db803-122">更新或卸载</span><span class="sxs-lookup"><span data-stu-id="db803-122">Update or uninstall</span></span>](../adapters-and-accelerators/update-or-uninstall-the-biztalk-adapter-pack-2016.md)