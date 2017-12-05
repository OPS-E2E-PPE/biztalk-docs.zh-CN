---
title: "运行的异常处理服务示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d69e720c-89e4-42c2-b4d0-31f0b865ab7f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dd7c87e84cf7e6e107fc110c611369d0407e003
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="running-the-exception-handling-service-sample"></a><span data-ttu-id="53678-102">运行的异常处理服务示例</span><span class="sxs-lookup"><span data-stu-id="53678-102">Running the Exception Handling Service Sample</span></span>
<span data-ttu-id="53678-103">异常处理服务示例演示如何使用异常处理 Web 服务以便提交到 ESB 异常处理框架从外部应用程序的错误。</span><span class="sxs-lookup"><span data-stu-id="53678-103">The Exception Handling Service sample demonstrates how to consume the Exception Handling Web Service in order to submit a fault into the ESB Exception Handling Framework from an external application.</span></span> <span data-ttu-id="53678-104">运行此示例的以下过程需要[安装异常管理示例](../esb-toolkit/installing-the-exception-management-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="53678-104">The following procedure for running this sample requires [Installing the Exception Management Samples](../esb-toolkit/installing-the-exception-management-samples.md).</span></span>  
  
 <span data-ttu-id="53678-105">**若要运行异常处理服务示例**</span><span class="sxs-lookup"><span data-stu-id="53678-105">**To run the Exception Handling Service sample**</span></span>  
  
1.  <span data-ttu-id="53678-106">在 Windows 资源管理器中打开文件夹 \Source\Samples\ExceptionHandlingService，其中安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后打开名为 ExceptionHandlingService.sln 的 Visual Studio 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="53678-106">In Windows Explorer, open the folder \Source\Samples\ExceptionHandlingService, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Visual Studio solution file named ExceptionHandlingService.sln.</span></span>  
  
2.  <span data-ttu-id="53678-107">在 Visual Studio 中，单击**启动调试**工具栏上。</span><span class="sxs-lookup"><span data-stu-id="53678-107">In Visual Studio, click **Start Debugging** on the Toolbar.</span></span>  
  
3.  <span data-ttu-id="53678-108">在加载表单中，单击**生成异常**按钮。</span><span class="sxs-lookup"><span data-stu-id="53678-108">On the form that loads, click the **Generate Exception** button.</span></span>  
  
4.  <span data-ttu-id="53678-109">在 Windows 资源管理器，依次打开文件夹 \Samples\Exception Handling\Test\Filedrop\All_Exceptions，和最新的 Exceptions_ {GUID}.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="53678-109">In Windows Explorer, open the folder \Samples\Exception Handling\Test\Filedrop\All_Exceptions, and then open the most recent Exceptions_{GUID}.xml file.</span></span>  
  
5.  <span data-ttu-id="53678-110">检查生成的异常的内容。</span><span class="sxs-lookup"><span data-stu-id="53678-110">Examine the contents of the generated exception.</span></span>  
  
 <span data-ttu-id="53678-111">有关如何在异常处理服务示例使用异常管理服务的详细信息，请参阅[异常处理服务示例的工作原理](../esb-toolkit/how-the-exception-handling-service-sample-works.md)。</span><span class="sxs-lookup"><span data-stu-id="53678-111">For more information about how the Exception Handling Service sample uses the Exception Management service, see [How the Exception Handling Service Sample Works](../esb-toolkit/how-the-exception-handling-service-sample-works.md).</span></span>