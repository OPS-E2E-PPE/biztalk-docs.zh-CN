---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 6b15d9d03ef967bcf7189ef756da8fc63a0eb3f6
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013676"
---
# <a name="how-to-create-send-ports-for-tibco-enterprise-message-service"></a><span data-ttu-id="ee419-101">如何创建 TIBCO Enterprise Message Service 的发送端口</span><span class="sxs-lookup"><span data-stu-id="ee419-101">How to Create Send Ports for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="ee419-102">请按照以下步骤创建发送端口。</span><span class="sxs-lookup"><span data-stu-id="ee419-102">Follow these steps to create a send port.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="ee419-103">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="ee419-103">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="ee419-104">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="ee419-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="ee419-105">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="ee419-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="ee419-106">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="ee419-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="ee419-107">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ee419-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="ee419-108">例如，键入发送端口的名称`SendToTIBCOEMS`。</span><span class="sxs-lookup"><span data-stu-id="ee419-108">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="ee419-109">从**类型**下拉列表中，选择**TIBCO EMS**。</span><span class="sxs-lookup"><span data-stu-id="ee419-109">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="ee419-110">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="ee419-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="ee419-111">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="ee419-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="ee419-112">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="ee419-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="ee419-113">单击**配置**配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="ee419-113">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="ee419-114">在**TIBCO EMS 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ee419-114">In the **TIBCO EMS Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="ee419-115">输入**消息处理**，**服务器连接定义**，**事务支持**，**用户名**，和**密码**。</span><span class="sxs-lookup"><span data-stu-id="ee419-115">Enter **Message Handling**, **Server Connection Definition**, **Transaction Support**, **Username**, and the **password**.</span></span>  
  
         <span data-ttu-id="ee419-116">您不必设置登录信息。</span><span class="sxs-lookup"><span data-stu-id="ee419-116">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="ee419-117">在列表中选择为表示 TIBCO EMS 系统所创建的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="ee419-117">In the list, select the affiliate application you created to represent the TIBCO EMS system.</span></span>  
  
    3.  <span data-ttu-id="ee419-118">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="ee419-118">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="ee419-119">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="ee419-119">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="ee419-120">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="ee419-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee419-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee419-121">See Also</span></span>  
  [<span data-ttu-id="ee419-122">创建 TIBCO Enterprise Message Service 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="ee419-122">Creating  TIBCO Enterprise Message Service Send Handlers</span></span>](../core/creating-tibco-enterprise-message-service-send-handlers.md)