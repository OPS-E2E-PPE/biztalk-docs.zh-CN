---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 2fbc1b4c16f94ef9397ff50a4e6d44d6aab051a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334234"
---
# <a name="how-to-set-send-pipelines-for-tibco-enterprise-message-service"></a><span data-ttu-id="9c285-101">如何设置 TIBCO Enterprise Message Service 的发送管道</span><span class="sxs-lookup"><span data-stu-id="9c285-101">How to Set Send Pipelines for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="9c285-102">用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器要求你选择 XMLTransmit 和 XMLReceive 的发送和接收管道分别。</span><span class="sxs-lookup"><span data-stu-id="9c285-102">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service requires that you select XMLTransmit and XMLReceive for the Send and Receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="9c285-103">若要设置管道</span><span class="sxs-lookup"><span data-stu-id="9c285-103">To set pipelines</span></span>  
  
1.  <span data-ttu-id="9c285-104">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c285-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="9c285-105">右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="9c285-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="9c285-106">在中**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9c285-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="9c285-107">例如，键入发送端口的名称`SendToTIBCOEMS`。</span><span class="sxs-lookup"><span data-stu-id="9c285-107">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="9c285-108">从**类型**下拉列表中，选择**TIBCO EMS**。</span><span class="sxs-lookup"><span data-stu-id="9c285-108">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="9c285-109">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="9c285-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="9c285-110">从发送管道下拉列表，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="9c285-110">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="9c285-111">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="9c285-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="9c285-112">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9c285-112">Click **OK**.</span></span>  
  
