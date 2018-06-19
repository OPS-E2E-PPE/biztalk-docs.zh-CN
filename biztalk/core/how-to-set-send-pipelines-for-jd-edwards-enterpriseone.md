---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 263f1f5d9441a30687df3e1a7a1170b7bf35e2fc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015068"
---
# <a name="how-to-set-send-pipelines-for-jd-edwards-enterpriseone"></a><span data-ttu-id="c89c0-101">如何设置 JD Edwards EnterpriseOne 的发送管道</span><span class="sxs-lookup"><span data-stu-id="c89c0-101">How to Set Send Pipelines for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="c89c0-102">Microsoft BizTalk Adapter for 博士 Edwards EnterpriseOne 要求你选择**XMLTransmit**和**XMLReceive**为发送和接收管道分别。</span><span class="sxs-lookup"><span data-stu-id="c89c0-102">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne requires that you select **XMLTransmit** and **XMLReceive** for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="c89c0-103">若要设置管道</span><span class="sxs-lookup"><span data-stu-id="c89c0-103">To set pipelines</span></span>  
  
1.  <span data-ttu-id="c89c0-104">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="c89c0-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="c89c0-105">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="c89c0-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="c89c0-106">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c89c0-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="c89c0-107">例如，键入发送端口的名称`SendToJDEEnterpriseOne`。</span><span class="sxs-lookup"><span data-stu-id="c89c0-107">Type a name for the send port, for example, `SendToJDEEnterpriseOne`.</span></span>  
  
    2.  <span data-ttu-id="c89c0-108">从**类型**下拉列表中，选择**JDE EnterpriseOne**。</span><span class="sxs-lookup"><span data-stu-id="c89c0-108">From the **Type** drop-down list, select **JDE EnterpriseOne**.</span></span>  
  
    3.  <span data-ttu-id="c89c0-109">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="c89c0-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="c89c0-110">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="c89c0-110">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="c89c0-111">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="c89c0-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="c89c0-112">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="c89c0-112">Click **OK**.</span></span>  
  
