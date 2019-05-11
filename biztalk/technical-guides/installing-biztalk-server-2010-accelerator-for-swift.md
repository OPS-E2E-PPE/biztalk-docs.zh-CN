---
title: 安装 BizTalk Server 2010 Accelerator for SWIFT |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d996ce-40ea-4d01-b083-c55ccace4b26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a68a49d89f31e3a025933c47c6475ee53aa0df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277123"
---
# <a name="installing-biztalk-server-2010-accelerator-for-swift"></a><span data-ttu-id="5a218-102">安装 BizTalk Server 2010 Accelerator for SWIFT</span><span class="sxs-lookup"><span data-stu-id="5a218-102">Installing BizTalk Server 2010 Accelerator for SWIFT</span></span>
<span data-ttu-id="5a218-103">![Logo](../technical-guides/media/bts-10-installaccelerator-logo.gif "BTS_10_InstallAccelerator_Logo")</span><span class="sxs-lookup"><span data-stu-id="5a218-103">![Logo](../technical-guides/media/bts-10-installaccelerator-logo.gif "BTS_10_InstallAccelerator_Logo")</span></span>  
  
 <span data-ttu-id="5a218-104">BizTalk 技术文章</span><span class="sxs-lookup"><span data-stu-id="5a218-104">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="5a218-105">**安装 BizTalk Server 2010 Accelerator for SWIFT**</span><span class="sxs-lookup"><span data-stu-id="5a218-105">**Installing BizTalk Server 2010 Accelerator for SWIFT**</span></span>  
  
 <span data-ttu-id="5a218-106">**编写器：** Maria Quian, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="5a218-106">**Writer:** Maria Quian, Microsoft Corporation</span></span>  
  
 <span data-ttu-id="5a218-107">**技术审阅人员：** Andres Naranjo、 Mandi Ohlinger</span><span class="sxs-lookup"><span data-stu-id="5a218-107">**Technical Reviewers:** Andres Naranjo, Mandi Ohlinger</span></span>  
  
 <span data-ttu-id="5a218-108">**发布日期：** 2012 年 6 月</span><span class="sxs-lookup"><span data-stu-id="5a218-108">**Published:** June 2012</span></span>  
  
 <span data-ttu-id="5a218-109">**适用于：** BizTalk Server 2010 Accelerator for SWIFT</span><span class="sxs-lookup"><span data-stu-id="5a218-109">**Applies To:** BizTalk Server 2010 Accelerator for SWIFT</span></span>  
  
 <span data-ttu-id="5a218-110">**摘要：** 成功安装的 Microsoft BizTalk Server 2010 Accelerator for SWIFT (A4SWIFT) 的基础是一种了解 A4SWIFT 功能以及每个功能所依赖的 BizTalk 组件。</span><span class="sxs-lookup"><span data-stu-id="5a218-110">**Summary:** The foundation for a successful installation of Microsoft BizTalk Server 2010 Accelerator for SWIFT (A4SWIFT) is an understanding of the A4SWIFT features and the BizTalk components on which each feature depends.</span></span> <span data-ttu-id="5a218-111">每个 A4SWIFT 功能依赖于其他正确配置的 BizTalk 组件。</span><span class="sxs-lookup"><span data-stu-id="5a218-111">Each A4SWIFT feature depends on other properly configured BizTalk components.</span></span> <span data-ttu-id="5a218-112">影响构建 A4SWIFT 环境的其他注意事项包括现有的网络基础结构和已配置的 BizTalk Server 环境。</span><span class="sxs-lookup"><span data-stu-id="5a218-112">Other considerations that affect building an A4SWIFT environment include an existing network infrastructure and an already configured BizTalk Server environment.</span></span> <span data-ttu-id="5a218-113">本文档将引用和用于构建 BizTalk Server 环境中使用的现有文档。</span><span class="sxs-lookup"><span data-stu-id="5a218-113">This document will refer and use the existing documentation for building BizTalk Server environments.</span></span> <span data-ttu-id="5a218-114">A4SWIFT 继承 BizTalk Server 2010 的所有软件和硬件要求。</span><span class="sxs-lookup"><span data-stu-id="5a218-114">A4SWIFT inherits all software and hardware requirements for BizTalk Server 2010.</span></span>  
  
 <span data-ttu-id="5a218-115">安装指南是可用于每个 A4SWIFT 相关的组件，但不是单个编译的文档，精心设计的安装/配置步骤。</span><span class="sxs-lookup"><span data-stu-id="5a218-115">An installation guide is available for each A4SWIFT related component but not a single compiled document that elaborates on the installation/configuration steps.</span></span> <span data-ttu-id="5a218-116">本文档会将它们组合在一起并标识一些安装和配置过程中遇到的常见问题。</span><span class="sxs-lookup"><span data-stu-id="5a218-116">This document will bring them together and identify some of the common issues encountered during installation and configuration.</span></span>  
  
 <span data-ttu-id="5a218-117">若要查看该文档，请下载[安装 BizTalk Server 2010 Accelerator for SWIFT](http://go.microsoft.com/fwlink/?LinkId=255118) Word 文档。</span><span class="sxs-lookup"><span data-stu-id="5a218-117">To review the document, please download the [Installing BizTalk Server 2010 Accelerator for SWIFT](http://go.microsoft.com/fwlink/?LinkId=255118) Word document.</span></span>