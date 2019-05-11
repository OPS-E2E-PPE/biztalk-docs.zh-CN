---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 4f579df64543ad21d923c37f6d97251d7655f552
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385460"
---
# <a name="how-to-create-receive-ports-in-tibco-enterprise-message-service"></a><span data-ttu-id="01943-101">如何创建 TIBCO Enterprise Message Service 中的接收端口</span><span class="sxs-lookup"><span data-stu-id="01943-101">How to Create Receive Ports in TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="01943-102">请按照下列步骤创建接收端口。</span><span class="sxs-lookup"><span data-stu-id="01943-102">Follow these steps to create a receive port.</span></span>  
  
### <a name="to-create-a-receive-port"></a><span data-ttu-id="01943-103">若要创建的接收端口</span><span class="sxs-lookup"><span data-stu-id="01943-103">To create a receive port</span></span>  
  
1.  <span data-ttu-id="01943-104">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="01943-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="01943-105">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="01943-105">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="01943-106">在中**接收端口属性**窗口，然后在**常规**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="01943-106">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="01943-107">在中**名称**字段中，键入`ReceiveFromTIBCOEMS`。</span><span class="sxs-lookup"><span data-stu-id="01943-107">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="01943-108">在中**身份验证**组框中，指定如何处理消息时使用身份验证。</span><span class="sxs-lookup"><span data-stu-id="01943-108">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="01943-109">选择**失败消息启用路由功能**复选框。</span><span class="sxs-lookup"><span data-stu-id="01943-109">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="01943-110">上**接收位置**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="01943-110">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="01943-111">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="01943-111">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="01943-112">在中**接收位置**窗口，然后在**常规**页上，键入**名称**的接收位置。</span><span class="sxs-lookup"><span data-stu-id="01943-112">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="01943-113">从**类型**下拉列表中，选择传输类型和从**接收处理程序**下拉列表中，选择的传输地址。</span><span class="sxs-lookup"><span data-stu-id="01943-113">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="01943-114">从**接收管道**下拉列表中，选择接收管道。</span><span class="sxs-lookup"><span data-stu-id="01943-114">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="01943-115">上**计划**页上，选择**开始日期**并**结束日期**以限制接收文档。</span><span class="sxs-lookup"><span data-stu-id="01943-115">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="01943-116">选择**启用服务时段**复选框。</span><span class="sxs-lookup"><span data-stu-id="01943-116">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="01943-117">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="01943-117">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="01943-118">上**入站映射**页上，选择用于转换所选端口上的文档的入站的映射。</span><span class="sxs-lookup"><span data-stu-id="01943-118">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="01943-119">上**跟踪**页上，选择所需的跟踪消息正文和跟踪消息属性。</span><span class="sxs-lookup"><span data-stu-id="01943-119">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="01943-120">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="01943-120">Click **OK**.</span></span>  
  
