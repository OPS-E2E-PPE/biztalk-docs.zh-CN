---
title: "如何创建一个适配器处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, handlers [adapters]
- handlers [adapters], creating
- adapters, handlers
ms.assetid: 09569417-dce6-473d-891f-6fd12347bcf0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e26caf02978006040e52ed3c62e520f51362e2c4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-create-an-adapter-handler"></a><span data-ttu-id="48590-102">如何创建一个适配器处理程序</span><span class="sxs-lookup"><span data-stu-id="48590-102">How to Create an Adapter Handler</span></span>
<span data-ttu-id="48590-103">可以使用 BizTalk Server 管理控制台来创建发送或接收适配器处理程序。</span><span class="sxs-lookup"><span data-stu-id="48590-103">You can create a send or receive adapter handler by using the BizTalk Server Administration Console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48590-104">您必须是 Single Sign-On Administrators 组的成员，才能创建适配器处理程序。</span><span class="sxs-lookup"><span data-stu-id="48590-104">You must be a member of the Single Sign-On Administrators group to create an adapter handler.</span></span>  
  
### <a name="to-create-an-adapter-handler"></a><span data-ttu-id="48590-105">创建适配器处理程序</span><span class="sxs-lookup"><span data-stu-id="48590-105">To create an adapter handler</span></span>  
  
1.  <span data-ttu-id="48590-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="48590-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="48590-107">在展开的适配器列表中，右键单击的适配器，你想要添加发送或接收处理程序，请指向**新建**，然后单击**发送处理程序**创建发送处理程序，或单击**接收处理者**创建接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="48590-107">In the expanded adapter list, right-click the adapter for which you would like to add a send or receive handler, point to **New**, and then click **Send Handler** to create a send handler or click **Receive Handler** to create a receive handler.</span></span>  
  
3.  <span data-ttu-id="48590-108">在**\<主机名\>属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择用的主机适配器处理程序将相关联。</span><span class="sxs-lookup"><span data-stu-id="48590-108">In the **\<host name\> Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the adapter handler will be associated.</span></span>  
  
4.  <span data-ttu-id="48590-109">如果要创建适配器发送处理程序，选择该选项以**将此项的默认处理**你是否希望此项为此适配器的默认发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="48590-109">If you are creating an adapter send handler, select the option to **Make this the default handler** if you would like for this to be the default send handler for this adapter.</span></span>  
  
5.  <span data-ttu-id="48590-110">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="48590-110">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48590-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48590-111">See Also</span></span>  
 [<span data-ttu-id="48590-112">创建和删除适配器处理程序</span><span class="sxs-lookup"><span data-stu-id="48590-112">Creating and Deleting Adapter Handlers</span></span>](../core/creating-and-deleting-adapter-handlers.md)