---
title: "运行 SQL 适配器示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13566d08-7a59-4065-b0d7-19ae2765555e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf04c06a1ef96974912ce3affe278d5a98936325
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-sql-adapter-sample"></a><span data-ttu-id="2a528-102">运行 SQL 适配器示例</span><span class="sxs-lookup"><span data-stu-id="2a528-102">Running the SQL Adapter Sample</span></span>
<span data-ttu-id="2a528-103">SQL 适配器示例使用了路线入口示例随附的 Windows 窗体测试客户端应用。</span><span class="sxs-lookup"><span data-stu-id="2a528-103">The SQL Adapter sample uses a Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="2a528-104">**若要运行 SQL 适配器示例**</span><span class="sxs-lookup"><span data-stu-id="2a528-104">**To run the SQL Adapter sample**</span></span>  
  
1.  <span data-ttu-id="2a528-105">如果 GlobalBank.ESB 应用程序尚未运行，使用 Microsoft BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="2a528-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="2a528-106">在 Windows 资源管理器，打开文件夹 \Source\Samples\Itinerary\Source\ESB。你的安装位置的 Itinerary.Test[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后启动指定 Esb.Itinerary.Test.exe 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2a528-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3.  <span data-ttu-id="2a528-107">清除**使用 WCF 服务**复选框，以便可以使用客户端路线。</span><span class="sxs-lookup"><span data-stu-id="2a528-107">Clear the **Use WCF Service** check box so that a client-side itinerary can be used.</span></span>  
  
4.  <span data-ttu-id="2a528-108">选择**两个方式服务**选项</span><span class="sxs-lookup"><span data-stu-id="2a528-108">Select the **Two Way Service** option</span></span>  
  
5.  <span data-ttu-id="2a528-109">单击**负载路线**按钮，，然后选择一个位于文件夹 \Source\Samples\SqlAdapter \Itineraries 示例路线。</span><span class="sxs-lookup"><span data-stu-id="2a528-109">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the folder \Source\Samples\SqlAdapter \Itineraries.</span></span>  
  
6.  <span data-ttu-id="2a528-110">单击**LoadMessage**按钮，，然后选择在文件夹 \Source\Samples\SqlAdapter \Test 中的 OrderDoc.xml 示例消息。</span><span class="sxs-lookup"><span data-stu-id="2a528-110">Click the **LoadMessage** button, and then select the OrderDoc.xml sample message in the folder \Source\Samples\SqlAdapter \Test.</span></span>  
  
7.  <span data-ttu-id="2a528-111">单击**SubmitRequest**按钮以将请求发送到路线提升服务。</span><span class="sxs-lookup"><span data-stu-id="2a528-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span>  
  
8.  <span data-ttu-id="2a528-112">请确保 GlobalBankESB 数据库的产品表中插入一行。</span><span class="sxs-lookup"><span data-stu-id="2a528-112">Make sure one row is inserted in the Product table of the GlobalBankESB database.</span></span>  
  
 <span data-ttu-id="2a528-113">有关 SQL 适配器示例的工作原理的信息，请参阅[SQL 适配器示例的工作原理](../esb-toolkit/how-the-sql-adapter-sample-works.md)。</span><span class="sxs-lookup"><span data-stu-id="2a528-113">For information about how the SQL Adapter sample works, see [How the SQL Adapter Sample Works](../esb-toolkit/how-the-sql-adapter-sample-works.md).</span></span>