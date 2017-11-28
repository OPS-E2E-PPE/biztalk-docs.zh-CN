---
title: "安装 JMS MQRFH2 组件示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a5bd855-512f-40a4-8038-ae9b847b1097
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b522d986524c77a53cf5a847f749a9ce41e2c50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-jms-mqrfh2-component-sample"></a><span data-ttu-id="c37d8-102">安装 JMS MQRFH2 组件示例</span><span class="sxs-lookup"><span data-stu-id="c37d8-102">Installing the JMS MQRFH2 Component Sample</span></span>
<span data-ttu-id="c37d8-103">若要使用此示例与[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，你还必须安装以下：</span><span class="sxs-lookup"><span data-stu-id="c37d8-103">To use this sample with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], you must also install the following:</span></span>  
  
-   <span data-ttu-id="c37d8-104">IBM WebSphere MQ 5.3 （与 CSD12)，WebSphere MQ 6.x 或 WebSphere MQ 7.0</span><span class="sxs-lookup"><span data-stu-id="c37d8-104">IBM WebSphere MQ 5.3 (with CSD12), WebSphere MQ 6.x or WebSphere MQ 7.0</span></span>  
  
-   <span data-ttu-id="c37d8-105">IBM"RfhUtil"JMS 测试实用程序以及队列检索消息</span><span class="sxs-lookup"><span data-stu-id="c37d8-105">The IBM "RfhUtil" JMS test utility for queuing and retrieving messages</span></span>  
  
 <span data-ttu-id="c37d8-106">JMS MQRFH2 组件示例要求要驻留在你的 Microsoft BizTalk Server 安装文件夹以及要驻留在全局程序集缓存中的相应架构 PipelineComponents 文件夹中的 JMS MQRFH2 组件。</span><span class="sxs-lookup"><span data-stu-id="c37d8-106">The JMS MQRFH2 Component sample requires the JMS MQRFH2 component to reside in the PipelineComponents folder of your Microsoft BizTalk Server installation folder and the corresponding schemas to reside in the global assembly cache.</span></span> <span data-ttu-id="c37d8-107">安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心自动复制，并将程序集安装到正确的位置。</span><span class="sxs-lookup"><span data-stu-id="c37d8-107">Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automatically copies and installs the assemblies to the correct locations.</span></span> <span data-ttu-id="c37d8-108">但是，如果需要，你可以手动执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="c37d8-108">However, if required, you can manually perform these tasks.</span></span>  
  
 <span data-ttu-id="c37d8-109">**若要手动安装的 JMS MQRFH2 组件和架构**</span><span class="sxs-lookup"><span data-stu-id="c37d8-109">**To manually install the JMS MQRFH2 component and schemas**</span></span>  
  
1.  <span data-ttu-id="c37d8-110">将程序集 Microsoft.Practices.ESB.JMS.PipelineComponents.dll 复制到你的 BizTalk Server 安装文件夹的 PipelineComponents 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c37d8-110">Copy the assembly Microsoft.Practices.ESB.JMS.PipelineComponents.dll to the PipelineComponents folder of your BizTalk Server installation folder.</span></span>  
  
2.  <span data-ttu-id="c37d8-111">添加到全局程序集缓存使用.NET Framework 配置工具的 Microsoft.Practices.ESB.JMS.Schemas.Property.dll 位于的管理工具部分中的架构程序集**启动**菜单。</span><span class="sxs-lookup"><span data-stu-id="c37d8-111">Add the schema assembly Microsoft.Practices.ESB.JMS.Schemas.Property.dll to the global assembly cache using the .NET Framework Configuration Tool located in the Administrative Tools section of the **Start** menu.</span></span>  
  
 <span data-ttu-id="c37d8-112">本部分介绍将 JMS MQRFH2 示例安装到 GlobalBank.JMS BizTalk 应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="c37d8-112">This section describes the process for installing the JMS MQRFH2 sample into the GlobalBank.JMS BizTalk application.</span></span> <span data-ttu-id="c37d8-113">在安装此示例之前，你必须安装 ESB 工具包核心中所述[安装 BizTalk ESB 工具包核心](http://go.microsoft.com/fwlink/?LinkId=187612)([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612))。</span><span class="sxs-lookup"><span data-stu-id="c37d8-113">Before you install this sample, you must install the ESB Toolkit Core as described in [Installing the BizTalk ESB Toolkit Core](http://go.microsoft.com/fwlink/?LinkId=187612) ([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612)).</span></span>  
  
 <span data-ttu-id="c37d8-114">可以从解决方案项目安装 JMS MQRFH2 组件示例，也可以使用随附的 Windows Installer 文件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c37d8-114">You can install the JMS MQRFH2 Component sample from the solution project or use the Windows Installer file included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="c37d8-115">本节包含下列主题：</span><span class="sxs-lookup"><span data-stu-id="c37d8-115">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="c37d8-116">安装使用安装脚本 JMS MQRFH2 示例</span><span class="sxs-lookup"><span data-stu-id="c37d8-116">Install the JMS MQRFH2 Sample Using the Install Scripts</span></span>](../esb-toolkit/install-the-jms-mqrfh2-sample-using-the-install-scripts.md)  
  
-   [<span data-ttu-id="c37d8-117">程序集和项目安装 JMS MQRFH2 组件示例</span><span class="sxs-lookup"><span data-stu-id="c37d8-117">Assemblies and Artifacts Installed by the JMS MQRFH2 Component Sample</span></span>](../esb-toolkit/assemblies-and-artifacts-installed-by-the-jms-mqrfh2-component-sample.md)  
  
-   [<span data-ttu-id="c37d8-118">测试 JMS MQRFH2 示例安装</span><span class="sxs-lookup"><span data-stu-id="c37d8-118">Test the JMS MQRFH2 Sample Installation</span></span>](../esb-toolkit/test-the-jms-mqrfh2-sample-installation.md)