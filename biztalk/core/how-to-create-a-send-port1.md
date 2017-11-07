---
title: "如何创建发送 Port1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: bf32e9f5-ebed-43d2-b9a9-6ab91925d973
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf49b16da34c5341059db34d6874b7099ab54df6
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-a-send-port"></a><span data-ttu-id="b1d12-102">如何创建发送端口</span><span class="sxs-lookup"><span data-stu-id="b1d12-102">How to Create a Send Port</span></span>
<span data-ttu-id="b1d12-103">使用下列过程来创建 JD Edwards EnterpriseOne 的 BizTalk Server 的发送端口。</span><span class="sxs-lookup"><span data-stu-id="b1d12-103">Use the following procedure to create BizTalk Server send ports for JD Edwards EnterpriseOne.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="b1d12-104">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="b1d12-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="b1d12-105">右键单击“发送端口”节点。</span><span class="sxs-lookup"><span data-stu-id="b1d12-105">Right-click the Send Ports node.</span></span>  
  
2.  <span data-ttu-id="b1d12-106">单击**添加发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b1d12-106">Click **Add Send Port**.</span></span>  
  
3.  <span data-ttu-id="b1d12-107">在**创建新发送端口**对话框中，选择**静态请求-响应端口**从**指定的一种发送端口**列表，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="b1d12-107">In the **Create New Send Port** dialog box, select **Static Solicit-Response Port** from the **Specify the type of Send Port** list, and click **OK**.</span></span>  
  
     <span data-ttu-id="b1d12-108">**静态请求-响应发送端口属性**窗口随即打开。</span><span class="sxs-lookup"><span data-stu-id="b1d12-108">The **Static Solicit-Response Send Port Properties** window opens.</span></span>  
  
4.  <span data-ttu-id="b1d12-109">例如，键入发送端口的名称`SSOSendToJDEEntOne`。</span><span class="sxs-lookup"><span data-stu-id="b1d12-109">Type a name for the send port, for example, `SSOSendToJDEEntOne`.</span></span>  
  
5.  <span data-ttu-id="b1d12-110">单击**传输**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b1d12-110">Click **Transport** in the left pane.</span></span>  
  
6.  <span data-ttu-id="b1d12-111">单击**传输类型**，然后选择**JDEEntOne**。</span><span class="sxs-lookup"><span data-stu-id="b1d12-111">Click **Transport Type**, and select **JDEEntOne**.</span></span>  
  
7.  <span data-ttu-id="b1d12-112">选择**地址 (URI)**，然后单击省略号 （…） 按钮。</span><span class="sxs-lookup"><span data-stu-id="b1d12-112">Select the **Address (URI)**, and click the ellipsis (…) button.</span></span>  
  
     <span data-ttu-id="b1d12-113">博士 Edwards EnterpriseOne**传输属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="b1d12-113">The JD Edwards EnterpriseOne **Transport Properties** dialog box appears.</span></span>  
  
8.  <span data-ttu-id="b1d12-114">类型`myJDEEntOneSSO`为**逻辑系统名称**。</span><span class="sxs-lookup"><span data-stu-id="b1d12-114">Type `myJDEEntOneSSO` for the **Logical System Name**.</span></span>  
  
9. <span data-ttu-id="b1d12-115">选择**是**为**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="b1d12-115">Select **Yes** for **Use SSO**.</span></span>  
  
10. <span data-ttu-id="b1d12-116">在下拉列表中，选择您创建代表 JD Edwards EnterpriseOne 系统的单一登录 (SSO) 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="b1d12-116">In the drop-down list, select the Single Sign-On (SSO) affiliate application that you created to represent the JD Edwards EnterpriseOne system.</span></span>  
  
     <span data-ttu-id="b1d12-117">单击**确定**以确认你输入的信息。</span><span class="sxs-lookup"><span data-stu-id="b1d12-117">Click **OK** to confirm the information you entered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d12-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1d12-118">See Also</span></span>  
 <span data-ttu-id="b1d12-119">[创建关联应用程序](../core/creating-affiliate-applications4.md) </span><span class="sxs-lookup"><span data-stu-id="b1d12-119">[Creating Affiliate Applications](../core/creating-affiliate-applications4.md) </span></span>  
 [<span data-ttu-id="b1d12-120">用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="b1d12-120">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)