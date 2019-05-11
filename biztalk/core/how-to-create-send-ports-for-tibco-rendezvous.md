---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: c3fe43f5ec5f69c84d9f679325a7437d84f2b7d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338923"
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a><span data-ttu-id="654cb-101">如何创建 TIBCO Rendezvous 的发送端口</span><span class="sxs-lookup"><span data-stu-id="654cb-101">How to Create Send Ports for TIBCO Rendezvous</span></span>
<span data-ttu-id="654cb-102">请遵循以下步骤创建发送端口使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="654cb-102">Follow these steps to create a send port using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="654cb-103">若要创建的发送端口</span><span class="sxs-lookup"><span data-stu-id="654cb-103">To create a send port</span></span>  
  
1.  <span data-ttu-id="654cb-104">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="654cb-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="654cb-105">右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="654cb-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="654cb-106">在中**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="654cb-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="654cb-107">例如，键入发送端口的名称`SendToTIBCORV`。</span><span class="sxs-lookup"><span data-stu-id="654cb-107">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="654cb-108">从**类型**下拉列表中，选择**TIBCO Rendezvous**。</span><span class="sxs-lookup"><span data-stu-id="654cb-108">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="654cb-109">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="654cb-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="654cb-110">从**发送管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="654cb-110">From the **Send Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span> <span data-ttu-id="654cb-111">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="654cb-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="654cb-112">单击**配置**可配置的发送端口。</span><span class="sxs-lookup"><span data-stu-id="654cb-112">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="654cb-113">在中**TIBCO Rendezvous 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="654cb-113">In the **TIBCO Rendezvous Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="654cb-114">输入的属性。</span><span class="sxs-lookup"><span data-stu-id="654cb-114">Enter the properties.</span></span>  
  
         <span data-ttu-id="654cb-115">不需要设置的登录信息。</span><span class="sxs-lookup"><span data-stu-id="654cb-115">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="654cb-116">在列表中，选择为表示 TIBCO Rendezvous 系统所创建的 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="654cb-116">In the list, select the SSO affiliate application you created to represent the TIBCO Rendezvous system.</span></span>  
  
    3.  <span data-ttu-id="654cb-117">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="654cb-117">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="654cb-118">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="654cb-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="654cb-119">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="654cb-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="654cb-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="654cb-120">See Also</span></span>  
 [<span data-ttu-id="654cb-121">创建 TIBCO Rendezvous 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="654cb-121">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)