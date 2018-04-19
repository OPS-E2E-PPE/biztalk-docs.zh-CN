---
title: 发布 （创建新消息） 的 MX 消息实例文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e6cdf4-b9db-42be-a92d-10a7471e2c2d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4082174428f177905527d0c648b4d7ad000dde36
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="publishing-the-mx-message-instance-file-creating-new-messages"></a><span data-ttu-id="4718f-102">发布 （创建新消息） 的 MX 消息实例文件</span><span class="sxs-lookup"><span data-stu-id="4718f-102">Publishing the MX Message Instance File (Creating New Messages)</span></span>
<span data-ttu-id="4718f-103">**若要发布 MX 消息实例文件：**</span><span class="sxs-lookup"><span data-stu-id="4718f-103">**To publish the MX message instance file:**</span></span>  
  
1.  <span data-ttu-id="4718f-104">转到在上一步中生成的 InfoPath 窗体模板的输出文件夹**...\\< MessageType\>\TemplateDS\InfoPath 窗体模板**。</span><span class="sxs-lookup"><span data-stu-id="4718f-104">Go to output folder of the InfoPath form template generated in the previous step **..\\<MessageType\>\TemplateDS\InfoPath Form Template**.</span></span>  
  
2.  <span data-ttu-id="4718f-105">在 Internet Explorer 中打开**http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**。</span><span class="sxs-lookup"><span data-stu-id="4718f-105">In Internet Explorer, open **http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**.</span></span>  
  
3.  <span data-ttu-id="4718f-106">在新 Swift MX 消息窗口中，单击**上载**。</span><span class="sxs-lookup"><span data-stu-id="4718f-106">In New Swift MX Messages window, click **Upload**.</span></span>  
  
4.  <span data-ttu-id="4718f-107">在上载文档窗口中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="4718f-107">In the Upload Document window, click **Browse**.</span></span>  
  
5.  <span data-ttu-id="4718f-108">在选择文件对话框中，移动到在上一步中生成的 InfoPath 窗体的输出文件夹**...\\< MessageType\>\TemplateDS\InfoPath 窗体模板**。</span><span class="sxs-lookup"><span data-stu-id="4718f-108">In the Choose file dialog box, move to the output folder of the InfoPath form generated in the previous step **..\\<MessageType\>\TemplateDS\InfoPath Form Template**.</span></span> <span data-ttu-id="4718f-109">选择\<MessageType\>.xml pacs.004.001.01.xml，如文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="4718f-109">Select the \<MessageType\>.xml file such as pacs.004.001.01.xml, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="4718f-110">在上载文档窗口中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4718f-110">In the Upload Document window, click **OK**.</span></span>  
  
7.  <span data-ttu-id="4718f-111">新建 SWIFT MX 消息中： \<MessageType\>窗口中的，Namespace 框中，键入 **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_ \<MessageType\>**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="4718f-111">In the New SWIFT MX Messages: \<MessageType\> window, in the Namespace box, type **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageType\>**, and then click **OK**.</span></span>