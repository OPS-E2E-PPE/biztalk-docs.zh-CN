---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 8f129c36e2f6765c76d76ee891ee297c0ccfeffe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338914"
---
# <a name="how-to-create-send-ports-for-peoplesoft-enterprise"></a><span data-ttu-id="f1938-101">如何创建适用于 PeopleSoft Enterprise 的发送端口</span><span class="sxs-lookup"><span data-stu-id="f1938-101">How to Create Send Ports for PeopleSoft Enterprise</span></span>
<span data-ttu-id="f1938-102">请按照以下步骤创建发送端口使用 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f1938-102">Follow these steps to create a send port using BizTalk Server Administration Console.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="f1938-103">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="f1938-103">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="f1938-104">若要创建的发送端口</span><span class="sxs-lookup"><span data-stu-id="f1938-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="f1938-105">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="f1938-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="f1938-106">右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="f1938-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="f1938-107">在中**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f1938-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="f1938-108">例如，键入发送端口的名称`SSOSendToPeopleSoft`。</span><span class="sxs-lookup"><span data-stu-id="f1938-108">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="f1938-109">从**类型**下拉列表中，选择**PeopleSoft**。</span><span class="sxs-lookup"><span data-stu-id="f1938-109">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="f1938-110">从**发送处理程序**下拉列表中，选择 URI。</span><span class="sxs-lookup"><span data-stu-id="f1938-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="f1938-111">从发送管道下拉列表，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="f1938-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="f1938-112">从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="f1938-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="f1938-113">单击**配置**可配置的发送端口。</span><span class="sxs-lookup"><span data-stu-id="f1938-113">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="f1938-114">在中**PeopleSoft 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f1938-114">In the **PeopleSoft Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="f1938-115">展开**适配器所需的属性**，并输入**应用程序服务器路径**， **JAVA_HOME**，**用户名**， **密码**，和用于连接到 Peoplesoft 系统的 Jar 文件。</span><span class="sxs-lookup"><span data-stu-id="f1938-115">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="f1938-116">不需要设置的登录信息。</span><span class="sxs-lookup"><span data-stu-id="f1938-116">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="f1938-117">在列表中，选择创建为表示 PeopleSoft 系统的 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="f1938-117">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="f1938-118">有关**使用 SSO**，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="f1938-118">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="f1938-119">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="f1938-119">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="f1938-120">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="f1938-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1938-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1938-121">See Also</span></span>  
 [<span data-ttu-id="f1938-122">创建 PeopleSoft 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="f1938-122">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)