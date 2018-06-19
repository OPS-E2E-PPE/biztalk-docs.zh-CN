---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 72cdd3553289df39442b71730a61e3271db381e7
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013140"
---
# <a name="how-to-set-send-pipelines-for-tibco-rendezvous"></a><span data-ttu-id="2483c-101">如何设置 TIBCO Rendezvous 的发送管道</span><span class="sxs-lookup"><span data-stu-id="2483c-101">How to Set Send Pipelines for TIBCO Rendezvous</span></span>
<span data-ttu-id="2483c-102">Microsoft BizTalk Adapter for TIBCO Rendezvous 要求您分别选择用于发送和接收管道的 XMLTransmit 和 XMLReceive。</span><span class="sxs-lookup"><span data-stu-id="2483c-102">Microsoft BizTalk Adapter for TIBCO Rendezvous requires that you select XMLTransmit and XMLReceive for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="2483c-103">若要设置管道</span><span class="sxs-lookup"><span data-stu-id="2483c-103">To set pipelines</span></span>  
  
1.  <span data-ttu-id="2483c-104">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="2483c-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="2483c-105">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="2483c-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="2483c-106">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2483c-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="2483c-107">例如，键入发送端口的名称`SendToTIBCORV`。</span><span class="sxs-lookup"><span data-stu-id="2483c-107">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="2483c-108">从**类型**下拉列表中，选择**TIBCO 会合**。</span><span class="sxs-lookup"><span data-stu-id="2483c-108">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="2483c-109">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="2483c-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="2483c-110">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="2483c-110">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="2483c-111">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="2483c-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="2483c-112">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="2483c-112">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2483c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2483c-113">See Also</span></span>  
 <span data-ttu-id="2483c-114">[创建 TIBCO 会合发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="2483c-114">[Creating TIBCO Rendezvous Send Handlers](../core/creating-tibco-rendezvous-send-handlers.md) </span></span>  
 [<span data-ttu-id="2483c-115">创建 TIBCO Rendezvou 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="2483c-115">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)