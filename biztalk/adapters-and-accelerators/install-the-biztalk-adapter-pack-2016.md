---
title: 安装 BizTalk 适配器包 2016年 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23c74470-6336-49be-95c3-32b5c279e0ab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24c3e0ba9087dd82eaf3fbd362179b109a6b9fc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364019"
---
# <a name="install-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="7d734-102">安装 BizTalk 适配器包 2016</span><span class="sxs-lookup"><span data-stu-id="7d734-102">Install the BizTalk Adapter Pack 2016</span></span>
## <a name="overview"></a><span data-ttu-id="7d734-103">概述</span><span class="sxs-lookup"><span data-stu-id="7d734-103">Overview</span></span>

<span data-ttu-id="7d734-104">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] (BAP) 随[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7d734-104">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] (BAP) is included with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="7d734-105">因此，当您下载[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，也要下载中的适配器[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7d734-105">So when you download [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], you are also downloading the adapters in the [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)].</span></span> 

<span data-ttu-id="7d734-106">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]使用[!INCLUDE[firstref_btsWinCommFoundation_md](../includes/firstref-btswincommfoundation-md.md)]与不同企业业务 (LOB) 系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="7d734-106">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] uses the [!INCLUDE[firstref_btsWinCommFoundation_md](../includes/firstref-btswincommfoundation-md.md)] to communicate with different enterprise line-of-business (LOB) systems.</span></span> <span data-ttu-id="7d734-107">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]有其自己的要求、 其自己的安装体验和它自己的安装步骤集。</span><span class="sxs-lookup"><span data-stu-id="7d734-107">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] has its own set of requirements, its own setup experience, and its own installation steps.</span></span> 

<span data-ttu-id="7d734-108">[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]是可选的并且如果你想仅需要[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]发送或接收到任何以下企业 LOB 系统的消息：</span><span class="sxs-lookup"><span data-stu-id="7d734-108">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] is optional, and is only needed if you want [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to send or receive messages to any of the following enterprise LOB systems:</span></span> 

* <span data-ttu-id="7d734-109">Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="7d734-109">Oracle Database</span></span>
* <span data-ttu-id="7d734-110">Oracle 电子商务套件 (EBS)</span><span class="sxs-lookup"><span data-stu-id="7d734-110">Oracle E-Business Suite (EBS)</span></span>
* <span data-ttu-id="7d734-111">SAP</span><span class="sxs-lookup"><span data-stu-id="7d734-111">SAP</span></span>
* <span data-ttu-id="7d734-112">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d734-112">SQL Server</span></span>
* <span data-ttu-id="7d734-113">Siebel</span><span class="sxs-lookup"><span data-stu-id="7d734-113">Siebel</span></span>

<span data-ttu-id="7d734-114">每个版本的[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]包含其自身[!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)]版本。</span><span class="sxs-lookup"><span data-stu-id="7d734-114">Every version of [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] includes its own [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] version.</span></span> <span data-ttu-id="7d734-115">该版本包含在你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本受支持。</span><span class="sxs-lookup"><span data-stu-id="7d734-115">Only the version included with your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] version is supported.</span></span> <span data-ttu-id="7d734-116">它们不是向后兼容。</span><span class="sxs-lookup"><span data-stu-id="7d734-116">They are not backward-compatible.</span></span>

<span data-ttu-id="7d734-117">本文档列出了用于安装 Microsoft BizTalk 适配器包 (BAP) 中包含的软件要求和步骤[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7d734-117">This document lists the software requirements, and the steps to install the Microsoft BizTalk Adapter Pack (BAP) included with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)].</span></span> 

## <a name="get-started-here"></a><span data-ttu-id="7d734-118">从此处开始</span><span class="sxs-lookup"><span data-stu-id="7d734-118">Get started here</span></span>
[<span data-ttu-id="7d734-119">软件先决条件</span><span class="sxs-lookup"><span data-stu-id="7d734-119">Software prerequisites</span></span>](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="7d734-120">安装步骤</span><span class="sxs-lookup"><span data-stu-id="7d734-120">Install steps</span></span>](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="7d734-121">安装后步骤</span><span class="sxs-lookup"><span data-stu-id="7d734-121">Post installation steps</span></span>](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="7d734-122">更新或卸载</span><span class="sxs-lookup"><span data-stu-id="7d734-122">Update or uninstall</span></span>](../adapters-and-accelerators/update-or-uninstall-the-biztalk-adapter-pack-2016.md)