---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: ec518c16383d847bf13706a6469b038b447c1543
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-send-ports-for-peoplesoft-enterprise"></a><span data-ttu-id="ed91d-101">如何创建 PeopleSoft Enterprise 的发送端口</span><span class="sxs-lookup"><span data-stu-id="ed91d-101">How to Create Send Ports for PeopleSoft Enterprise</span></span>
<span data-ttu-id="ed91d-102">请按照下列步骤以创建发送端口使用 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ed91d-102">Follow these steps to create a send port using BizTalk Server Administration Console.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="ed91d-103">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="ed91d-103">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="ed91d-104">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="ed91d-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="ed91d-105">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed91d-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="ed91d-106">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="ed91d-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="ed91d-107">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ed91d-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="ed91d-108">例如，键入发送端口的名称`SSOSendToPeopleSoft`。</span><span class="sxs-lookup"><span data-stu-id="ed91d-108">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="ed91d-109">从**类型**下拉列表中，选择**PeopleSoft**。</span><span class="sxs-lookup"><span data-stu-id="ed91d-109">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="ed91d-110">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="ed91d-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="ed91d-111">从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="ed91d-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="ed91d-112">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="ed91d-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="ed91d-113">单击**配置**配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="ed91d-113">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="ed91d-114">在**PeopleSoft 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ed91d-114">In the **PeopleSoft Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="ed91d-115">展开**适配器所需属性**，并输入**应用程序服务器路径**， **JAVA_HOME**，**用户名**， **密码**，和连接到 Peoplesoft 系统的 Jar 文件。</span><span class="sxs-lookup"><span data-stu-id="ed91d-115">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="ed91d-116">您不必设置登录信息。</span><span class="sxs-lookup"><span data-stu-id="ed91d-116">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="ed91d-117">在列表中选择为表示 PeopleSoft 系统所创建的 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed91d-117">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="ed91d-118">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="ed91d-118">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="ed91d-119">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="ed91d-119">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="ed91d-120">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="ed91d-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed91d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed91d-121">See Also</span></span>  
 [<span data-ttu-id="ed91d-122">创建 PeopleSoft 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="ed91d-122">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)