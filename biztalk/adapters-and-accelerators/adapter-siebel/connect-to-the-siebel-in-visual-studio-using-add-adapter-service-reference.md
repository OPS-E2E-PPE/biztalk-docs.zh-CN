---
title: "连接到 Siebel 系统在 Visual Studio 使用添加适配器服务引用插件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d27121be-6407-4bb6-acb5-37dc8a3785c0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 696e91d689bfc7bc058ce0c512e8fa09b91b18a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="d2624-102">连接到 Siebel 系统在 Visual Studio 使用添加插件的适配器服务引用</span><span class="sxs-lookup"><span data-stu-id="d2624-102">Connect to the Siebel System in Visual Studio Using Add Adapter Service Reference Plug-in</span></span>
<span data-ttu-id="d2624-103">若要连接到 Siebel 系统使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在.NET 编程解决方案中，你必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d2624-103">To connect to a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in a .NET programming solution, you must use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="d2624-104">本主题将说明了如何使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d2624-104">This topic provides instructions on how to use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="connecting-to-a-siebel-system-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="d2624-105">连接到使用 Siebel 系统添加插件的适配器服务引用</span><span class="sxs-lookup"><span data-stu-id="d2624-105">Connecting to a Siebel System Using Add Adapter Service Reference Plug-in</span></span>  
 <span data-ttu-id="d2624-106">执行以下步骤以连接到 Siebel 系统使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d2624-106">Perform the following steps to connect to a Siebel system using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
#### <a name="to-connect-to-a-siebel-system"></a><span data-ttu-id="d2624-107">若要连接到 Siebel 系统</span><span class="sxs-lookup"><span data-stu-id="d2624-107">To connect to a Siebel system</span></span>  
  
1.  <span data-ttu-id="d2624-108">若要使用连接[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="d2624-108">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="d2624-109">创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d2624-109">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="d2624-110">右键单击解决方案资源管理器中的项目，然后单击**添加适配器服务引用**。</span><span class="sxs-lookup"><span data-stu-id="d2624-110">Right-click the project in Solution Explorer, and then click **Add Adapter Service Reference**.</span></span> <span data-ttu-id="d2624-111">此时[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="d2624-111">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] opens.</span></span>  
  
2.  <span data-ttu-id="d2624-112">从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d2624-112">From the **Select a binding** drop-down list, select **siebelBinding**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="d2624-113">在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**.</span><span class="sxs-lookup"><span data-stu-id="d2624-113">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username**.</span></span>  
  
4.  <span data-ttu-id="d2624-114">指定的用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="d2624-114">Specify the user name and password to connect to the Siebel system.</span></span>  
  
5.  <span data-ttu-id="d2624-115">单击**URI 属性**选项卡，然后指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="d2624-115">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="d2624-116">有关连接 URI 的详细信息为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="d2624-116">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d2624-117">如果连接参数包含任何保留的字符，则必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。</span><span class="sxs-lookup"><span data-stu-id="d2624-117">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="d2624-118">但是，如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。</span><span class="sxs-lookup"><span data-stu-id="d2624-118">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
6.  <span data-ttu-id="d2624-119">单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。</span><span class="sxs-lookup"><span data-stu-id="d2624-119">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="d2624-120">有关绑定属性的详细信息，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d2624-120">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
7.  <span data-ttu-id="d2624-121">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d2624-121">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="d2624-122">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="d2624-122">Click **Connect**.</span></span> <span data-ttu-id="d2624-123">一旦建立连接，连接状态将显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="d2624-123">Once the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="d2624-124">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="d2624-124">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span> <span data-ttu-id="d2624-125">图形用户界面是适用于[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d2624-125">The graphical user interface is same for the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
     <span data-ttu-id="d2624-126">![使用适配器服务连接的对话框](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span><span class="sxs-lookup"><span data-stu-id="d2624-126">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span></span>  
  
     <span data-ttu-id="d2624-127">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]显示包含可以在 Siebel 系统执行的各种操作的不同节点。</span><span class="sxs-lookup"><span data-stu-id="d2624-127">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] displays different nodes containing various operations that can be performed on the Siebel system.</span></span> <span data-ttu-id="d2624-128">例如，**业务对象**节点包含所有的业务对象和可以调用 Siebel 系统的业务组件。</span><span class="sxs-lookup"><span data-stu-id="d2624-128">For example, the **Business Objects** node contains all the business objects and business components that can be invoked on the Siebel system.</span></span> <span data-ttu-id="d2624-129">同样，**业务服务**节点连接到 Siebel 系统中包含所有业务服务。</span><span class="sxs-lookup"><span data-stu-id="d2624-129">Similarly, the **Business Services**  node contains all the business services in the Siebel system you connected to.</span></span> <span data-ttu-id="d2624-130">有关这些节点的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)。</span><span class="sxs-lookup"><span data-stu-id="d2624-130">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span></span>