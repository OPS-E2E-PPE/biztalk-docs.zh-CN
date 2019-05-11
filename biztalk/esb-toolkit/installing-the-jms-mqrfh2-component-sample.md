---
title: 安装 JMS MQRFH2 组件示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5bd855-512f-40a4-8038-ae9b847b1097
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4d1ddc49c882ecff05083e9a0a38357733f7f9e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249770"
---
# <a name="installing-the-jms-mqrfh2-component-sample"></a><span data-ttu-id="4108c-102">安装 JMS MQRFH2 组件示例</span><span class="sxs-lookup"><span data-stu-id="4108c-102">Installing the JMS MQRFH2 Component Sample</span></span>
<span data-ttu-id="4108c-103">若要使用此示例与[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，还必须安装以下：</span><span class="sxs-lookup"><span data-stu-id="4108c-103">To use this sample with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], you must also install the following:</span></span>  
  
- <span data-ttu-id="4108c-104">IBM WebSphere MQ 5.3 （带有 CSD12)，WebSphere MQ 6.x 或 WebSphere MQ 7.0</span><span class="sxs-lookup"><span data-stu-id="4108c-104">IBM WebSphere MQ 5.3 (with CSD12), WebSphere MQ 6.x or WebSphere MQ 7.0</span></span>  
  
- <span data-ttu-id="4108c-105">IBM"RfhUtil"JMS 测试实用程序，用于队列和检索消息</span><span class="sxs-lookup"><span data-stu-id="4108c-105">The IBM "RfhUtil" JMS test utility for queuing and retrieving messages</span></span>  
  
  <span data-ttu-id="4108c-106">JMS MQRFH2 组件示例要求要驻留在你的 Microsoft BizTalk Server 安装文件夹和相应的架构在全局程序集缓存中驻留的 PipelineComponents 文件夹中的 JMS MQRFH2 组件。</span><span class="sxs-lookup"><span data-stu-id="4108c-106">The JMS MQRFH2 Component sample requires the JMS MQRFH2 component to reside in the PipelineComponents folder of your Microsoft BizTalk Server installation folder and the corresponding schemas to reside in the global assembly cache.</span></span> <span data-ttu-id="4108c-107">安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]core 自动复制，并将程序集安装到正确的位置。</span><span class="sxs-lookup"><span data-stu-id="4108c-107">Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automatically copies and installs the assemblies to the correct locations.</span></span> <span data-ttu-id="4108c-108">但是，如果需要，你可以手动执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="4108c-108">However, if required, you can manually perform these tasks.</span></span>  
  
  <span data-ttu-id="4108c-109">**若要手动安装 JMS MQRFH2 组件和架构**</span><span class="sxs-lookup"><span data-stu-id="4108c-109">**To manually install the JMS MQRFH2 component and schemas**</span></span>  
  
1. <span data-ttu-id="4108c-110">将程序集 Microsoft.Practices.ESB.JMS.PipelineComponents.dll 复制到 PipelineComponents 文件夹的 BizTalk Server 安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="4108c-110">Copy the assembly Microsoft.Practices.ESB.JMS.PipelineComponents.dll to the PipelineComponents folder of your BizTalk Server installation folder.</span></span>  
  
2. <span data-ttu-id="4108c-111">添加架构程序集使用.NET Framework 配置工具在全局程序集缓存到 Microsoft.Practices.ESB.JMS.Schemas.Property.dll 位于中的管理工具部分**启动**菜单。</span><span class="sxs-lookup"><span data-stu-id="4108c-111">Add the schema assembly Microsoft.Practices.ESB.JMS.Schemas.Property.dll to the global assembly cache using the .NET Framework Configuration Tool located in the Administrative Tools section of the **Start** menu.</span></span>  
  
   <span data-ttu-id="4108c-112">本部分介绍 JMS MQRFH2 示例安装到 GlobalBank.JMS BizTalk 应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="4108c-112">This section describes the process for installing the JMS MQRFH2 sample into the GlobalBank.JMS BizTalk application.</span></span> <span data-ttu-id="4108c-113">在安装此示例之前，如中所述，您必须安装 ESB 工具包内核[安装 BizTalk ESB 工具包 Core](http://go.microsoft.com/fwlink/?LinkId=187612) ([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612))。</span><span class="sxs-lookup"><span data-stu-id="4108c-113">Before you install this sample, you must install the ESB Toolkit Core as described in [Installing the BizTalk ESB Toolkit Core](http://go.microsoft.com/fwlink/?LinkId=187612) ([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612)).</span></span>  
  
   <span data-ttu-id="4108c-114">可以从解决方案项目中安装 JMS MQRFH2 组件示例，也可以使用随附的 Windows 安装程序文件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4108c-114">You can install the JMS MQRFH2 Component sample from the solution project or use the Windows Installer file included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="4108c-115">本节包含下列主题：</span><span class="sxs-lookup"><span data-stu-id="4108c-115">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="4108c-116">使用安装脚本安装 JMS MQRFH2 示例</span><span class="sxs-lookup"><span data-stu-id="4108c-116">Install the JMS MQRFH2 Sample Using the Install Scripts</span></span>](../esb-toolkit/install-the-jms-mqrfh2-sample-using-the-install-scripts.md)  
  
-   [<span data-ttu-id="4108c-117">JMS MQRFH2 组件示例安装的程序集和项目</span><span class="sxs-lookup"><span data-stu-id="4108c-117">Assemblies and Artifacts Installed by the JMS MQRFH2 Component Sample</span></span>](../esb-toolkit/assemblies-and-artifacts-installed-by-the-jms-mqrfh2-component-sample.md)  
  
-   [<span data-ttu-id="4108c-118">测试 JMS MQRFH2 示例安装</span><span class="sxs-lookup"><span data-stu-id="4108c-118">Test the JMS MQRFH2 Sample Installation</span></span>](../esb-toolkit/test-the-jms-mqrfh2-sample-installation.md)