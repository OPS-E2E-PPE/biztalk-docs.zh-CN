---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 44da7839f0bee96db332dada214bdbc503067f56
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013156"
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a><span data-ttu-id="d8556-101">如何创建 TIBCO Rendezvous 的发送端口</span><span class="sxs-lookup"><span data-stu-id="d8556-101">How to Create Send Ports for TIBCO Rendezvous</span></span>
<span data-ttu-id="d8556-102">请按照以下步骤，使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 创建一个发送端口。</span><span class="sxs-lookup"><span data-stu-id="d8556-102">Follow these steps to create a send port using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="d8556-103">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="d8556-103">To create a send port</span></span>  
  
1.  <span data-ttu-id="d8556-104">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="d8556-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="d8556-105">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d8556-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="d8556-106">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d8556-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="d8556-107">例如，键入发送端口的名称`SendToTIBCORV`。</span><span class="sxs-lookup"><span data-stu-id="d8556-107">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="d8556-108">从**类型**下拉列表中，选择**TIBCO 会合**。</span><span class="sxs-lookup"><span data-stu-id="d8556-108">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="d8556-109">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="d8556-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="d8556-110">从**发送管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="d8556-110">From the **Send Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span> <span data-ttu-id="d8556-111">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="d8556-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="d8556-112">单击**配置**配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="d8556-112">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="d8556-113">在**TIBCO 会合传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d8556-113">In the **TIBCO Rendezvous Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="d8556-114">输入属性。</span><span class="sxs-lookup"><span data-stu-id="d8556-114">Enter the properties.</span></span>  
  
         <span data-ttu-id="d8556-115">您不必设置登录信息。</span><span class="sxs-lookup"><span data-stu-id="d8556-115">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="d8556-116">在列表中，选择 SSO 关联应用程序创建的用来表示 TIBCO 会合系统。</span><span class="sxs-lookup"><span data-stu-id="d8556-116">In the list, select the SSO affiliate application you created to represent the TIBCO Rendezvous system.</span></span>  
  
    3.  <span data-ttu-id="d8556-117">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="d8556-117">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="d8556-118">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d8556-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="d8556-119">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d8556-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8556-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8556-120">See Also</span></span>  
 [<span data-ttu-id="d8556-121">创建 TIBCO Rendezvous 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="d8556-121">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)