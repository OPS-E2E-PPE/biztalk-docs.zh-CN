---
title: "连接到 Siebel 系统在 Visual Studio 使用添加适配器元数据向导 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0a82fcc-b3ac-4936-9210-03c99d3741d7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9fc38299ffdce6cf6227cacb7de0cae84b22091
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="d4087-102">连接到 Siebel 系统在 Visual Studio 使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="d4087-102">Connect to the Siebel System in Visual Studio Using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="d4087-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]名称还公开为 BizTalk 适配器，因此，你可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要为你想要在 Siebel 系统使用该适配器上执行的操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="d4087-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is also exposed as a BizTalk adapter and hence, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on the Siebel system using the adapter.</span></span>  
  
## <a name="connecting-to-a-siebel-system-using-add-adapter-metadata-wizard"></a><span data-ttu-id="d4087-104">连接到 Siebel 系统使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="d4087-104">Connecting to a Siebel System Using Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="d4087-105">执行以下步骤以连接到 Siebel 系统使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d4087-105">Perform the following steps to connect to a Siebel system using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-connect-to-a-siebel-system"></a><span data-ttu-id="d4087-106">若要连接到 Siebel 系统</span><span class="sxs-lookup"><span data-stu-id="d4087-106">To connect to a Siebel system</span></span>  
  
1.  <span data-ttu-id="d4087-107">若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="d4087-107">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="d4087-108">创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d4087-108">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="d4087-109">右键单击解决方案资源管理器中的项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="d4087-109">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
    3.  <span data-ttu-id="d4087-110">在**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4087-110">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="d4087-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d4087-111">Use this</span></span>|<span data-ttu-id="d4087-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d4087-112">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="d4087-113">**类别**</span><span class="sxs-lookup"><span data-stu-id="d4087-113">**Categories**</span></span>|<span data-ttu-id="d4087-114">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="d4087-114">Click **Consume Adapter Service**.</span></span>|  
        |<span data-ttu-id="d4087-115">**模板**</span><span class="sxs-lookup"><span data-stu-id="d4087-115">**Templates**</span></span>|<span data-ttu-id="d4087-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="d4087-116">Click **Consume Adapter Service**.</span></span>|  
  
    4.  <span data-ttu-id="d4087-117">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="d4087-117">Click **Add**.</span></span> <span data-ttu-id="d4087-118">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="d4087-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
    5.  <span data-ttu-id="d4087-119">在[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，选择 WCF Siebel。</span><span class="sxs-lookup"><span data-stu-id="d4087-119">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select WCF-Siebel.</span></span> <span data-ttu-id="d4087-120">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="d4087-120">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="d4087-121">如果你已有**WCF Siebel**端口中配置的 BizTalk，选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="d4087-121">If you already have a **WCF-Siebel** port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
    6.  <span data-ttu-id="d4087-122">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="d4087-122">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="d4087-123">从**选择的绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d4087-123">From the **Select a binding** drop-down list, select **siebelBinding**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="d4087-124">在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**.</span><span class="sxs-lookup"><span data-stu-id="d4087-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username**.</span></span>  
  
4.  <span data-ttu-id="d4087-125">指定的用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="d4087-125">Specify the user name and password to connect to the Siebel system.</span></span>  
  
5.  <span data-ttu-id="d4087-126">单击**URI 属性**选项卡，然后指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="d4087-126">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="d4087-127">有关连接 URI 的详细信息为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="d4087-127">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4087-128">如果连接参数包含任何保留的字符，则必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。</span><span class="sxs-lookup"><span data-stu-id="d4087-128">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="d4087-129">但是，如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。</span><span class="sxs-lookup"><span data-stu-id="d4087-129">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
6.  <span data-ttu-id="d4087-130">单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。</span><span class="sxs-lookup"><span data-stu-id="d4087-130">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="d4087-131">有关绑定属性的详细信息，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d4087-131">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4087-132">如果正在生成元数据中使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]并且选择现有 WCF Siebel 发送端口，你不需要指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="d4087-132">If you are generating metadata using [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] and you selected an existing WCF-Siebel send port, you need not specify the binding properties.</span></span> <span data-ttu-id="d4087-133">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="d4087-133">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="d4087-134">但是，你可以选择指定所需在设计时，如果任何绑定属性。</span><span class="sxs-lookup"><span data-stu-id="d4087-134">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="d4087-135">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="d4087-135">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="d4087-136">但是，在运行时指定中发送端口配置的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="d4087-136">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
7.  <span data-ttu-id="d4087-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d4087-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="d4087-138">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="d4087-138">Click **Connect**.</span></span> <span data-ttu-id="d4087-139">一旦建立连接，连接状态将显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="d4087-139">Once the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="d4087-140">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="d4087-140">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  
  
     <span data-ttu-id="d4087-141">![使用适配器服务连接的对话框](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span><span class="sxs-lookup"><span data-stu-id="d4087-141">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span></span>  
  
     <span data-ttu-id="d4087-142">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在 Siebel 系统执行的各种操作的不同节点。</span><span class="sxs-lookup"><span data-stu-id="d4087-142">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on the Siebel system.</span></span> <span data-ttu-id="d4087-143">例如，**业务对象**节点包含所有的业务对象和可以调用 Siebel 系统的业务组件。</span><span class="sxs-lookup"><span data-stu-id="d4087-143">For example, the **Business Objects** node contains all the business objects and business components that can be invoked on the Siebel system.</span></span> <span data-ttu-id="d4087-144">同样，**业务服务**节点连接到 Siebel 系统中包含所有业务服务。</span><span class="sxs-lookup"><span data-stu-id="d4087-144">Similarly, the **Business Services**  node contains all the business services in the Siebel system you connected to.</span></span> <span data-ttu-id="d4087-145">有关这些节点的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)。</span><span class="sxs-lookup"><span data-stu-id="d4087-145">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span></span>