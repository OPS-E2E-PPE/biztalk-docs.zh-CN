---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 2681c3141f6c89479c3632b1a00f35ee495aa4b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383925"
---
# <a name="how-to-set-pipelines-for-peoplesoft-enterprise"></a><span data-ttu-id="f6c08-101">如何设置适用于 PeopleSoft Enterprise 的管道</span><span class="sxs-lookup"><span data-stu-id="f6c08-101">How to Set Pipelines for PeopleSoft Enterprise</span></span>
<span data-ttu-id="f6c08-102">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器要求选择适当的管道。</span><span class="sxs-lookup"><span data-stu-id="f6c08-102">Microsoft BizTalk Adapter for PeopleSoft Enterprise requires that you select an appropriate pipeline.</span></span>  
  
## <a name="setting-pipelines"></a><span data-ttu-id="f6c08-103">设置管道</span><span class="sxs-lookup"><span data-stu-id="f6c08-103">Setting Pipelines</span></span>  
  
#### <a name="to-set-pipelines"></a><span data-ttu-id="f6c08-104">若要设置管道</span><span class="sxs-lookup"><span data-stu-id="f6c08-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="f6c08-105">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="f6c08-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="f6c08-106">右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="f6c08-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="f6c08-107">在中**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f6c08-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="f6c08-108">例如，键入发送端口的名称`SSOSendToPeopleSoft`。</span><span class="sxs-lookup"><span data-stu-id="f6c08-108">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="f6c08-109">从**类型**下拉列表中，选择**PeopleSoft**。</span><span class="sxs-lookup"><span data-stu-id="f6c08-109">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="f6c08-110">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="f6c08-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="f6c08-111">从发送管道下拉列表，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="f6c08-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="f6c08-112">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="f6c08-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="f6c08-113">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="f6c08-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6c08-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6c08-114">See Also</span></span>  
 [<span data-ttu-id="f6c08-115">创建 PeopleSoft 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="f6c08-115">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)