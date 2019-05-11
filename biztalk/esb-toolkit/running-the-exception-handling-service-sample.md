---
title: 运行异常处理服务示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d69e720c-89e4-42c2-b4d0-31f0b865ab7f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17a1460b1248aa64ba043e8e6c01a66dc6215490
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242860"
---
# <a name="running-the-exception-handling-service-sample"></a><span data-ttu-id="97784-102">运行异常处理服务示例</span><span class="sxs-lookup"><span data-stu-id="97784-102">Running the Exception Handling Service Sample</span></span>
<span data-ttu-id="97784-103">异常处理服务示例演示如何使用异常处理 Web 服务才能提交到 ESB 异常处理框架从外部应用程序的错误。</span><span class="sxs-lookup"><span data-stu-id="97784-103">The Exception Handling Service sample demonstrates how to consume the Exception Handling Web Service in order to submit a fault into the ESB Exception Handling Framework from an external application.</span></span> <span data-ttu-id="97784-104">有关运行此示例的以下过程要求[安装异常管理示例](../esb-toolkit/installing-the-exception-management-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="97784-104">The following procedure for running this sample requires [Installing the Exception Management Samples](../esb-toolkit/installing-the-exception-management-samples.md).</span></span>  
  
 <span data-ttu-id="97784-105">**若要运行异常处理服务示例**</span><span class="sxs-lookup"><span data-stu-id="97784-105">**To run the Exception Handling Service sample**</span></span>  
  
1. <span data-ttu-id="97784-106">在 Windows 资源管理器中打开文件夹 \Source\Samples\ExceptionHandlingService，其中安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，并打开名为 ExceptionHandlingService.sln Visual Studio 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="97784-106">In Windows Explorer, open the folder \Source\Samples\ExceptionHandlingService, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Visual Studio solution file named ExceptionHandlingService.sln.</span></span>  
  
2. <span data-ttu-id="97784-107">在 Visual Studio 中，单击**启动调试**工具栏上。</span><span class="sxs-lookup"><span data-stu-id="97784-107">In Visual Studio, click **Start Debugging** on the Toolbar.</span></span>  
  
3. <span data-ttu-id="97784-108">在加载表单中，单击**生成异常**按钮。</span><span class="sxs-lookup"><span data-stu-id="97784-108">On the form that loads, click the **Generate Exception** button.</span></span>  
  
4. <span data-ttu-id="97784-109">在 Windows 资源管理器，打开文件夹 \Samples\Exception Handling\Test\Filedrop\All_Exceptions，并打开的最新的 Exceptions_ {GUID}.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="97784-109">In Windows Explorer, open the folder \Samples\Exception Handling\Test\Filedrop\All_Exceptions, and then open the most recent Exceptions_{GUID}.xml file.</span></span>  
  
5. <span data-ttu-id="97784-110">检查生成的异常的内容。</span><span class="sxs-lookup"><span data-stu-id="97784-110">Examine the contents of the generated exception.</span></span>  
  
   <span data-ttu-id="97784-111">有关异常处理服务示例如何使用异常管理服务的详细信息，请参阅[异常处理服务示例的工作原理](../esb-toolkit/how-the-exception-handling-service-sample-works.md)。</span><span class="sxs-lookup"><span data-stu-id="97784-111">For more information about how the Exception Handling Service sample uses the Exception Management service, see [How the Exception Handling Service Sample Works](../esb-toolkit/how-the-exception-handling-service-sample-works.md).</span></span>