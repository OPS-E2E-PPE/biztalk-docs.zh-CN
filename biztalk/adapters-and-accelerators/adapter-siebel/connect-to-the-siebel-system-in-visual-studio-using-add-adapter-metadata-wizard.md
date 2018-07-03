---
title: 连接到 Siebel 系统中 Visual Studio 中使用添加适配器元数据向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0a82fcc-b3ac-4936-9210-03c99d3741d7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 700c2ad92cd03b50808f6a785b34b4d745482acb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983486"
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="2ede0-102">连接到 Siebel 系统中 Visual Studio 中使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="2ede0-102">Connect to the Siebel System in Visual Studio Using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="2ede0-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]还会显示为 BizTalk 适配器，因此，可以使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]来为你想要使用的适配器在 Siebel 系统上执行的操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="2ede0-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is also exposed as a BizTalk adapter and hence, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on the Siebel system using the adapter.</span></span>  

## <a name="connecting-to-a-siebel-system-using-add-adapter-metadata-wizard"></a><span data-ttu-id="2ede0-104">连接到 Siebel 系统使用添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="2ede0-104">Connecting to a Siebel System Using Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="2ede0-105">执行以下步骤连接到 Siebel 系统[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2ede0-105">Perform the following steps to connect to a Siebel system using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="to-connect-to-a-siebel-system"></a><span data-ttu-id="2ede0-106">若要连接到 Siebel 系统</span><span class="sxs-lookup"><span data-stu-id="2ede0-106">To connect to a Siebel system</span></span>  

1. <span data-ttu-id="2ede0-107">若要使用连接[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="2ede0-107">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="2ede0-108">创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2ede0-108">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

   2. <span data-ttu-id="2ede0-109">右键单击解决方案资源管理器中的项目，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="2ede0-109">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   3. <span data-ttu-id="2ede0-110">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2ede0-110">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="2ede0-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="2ede0-111">Use this</span></span>    |             <span data-ttu-id="2ede0-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="2ede0-112">To do this</span></span>             |
      |----------------|------------------------------------|
      | <span data-ttu-id="2ede0-113">**类别**</span><span class="sxs-lookup"><span data-stu-id="2ede0-113">**Categories**</span></span> | <span data-ttu-id="2ede0-114">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="2ede0-114">Click **Consume Adapter Service**.</span></span> |
      | <span data-ttu-id="2ede0-115">**模板**</span><span class="sxs-lookup"><span data-stu-id="2ede0-115">**Templates**</span></span>  | <span data-ttu-id="2ede0-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="2ede0-116">Click **Consume Adapter Service**.</span></span> |


   4. <span data-ttu-id="2ede0-117">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="2ede0-117">Click **Add**.</span></span> <span data-ttu-id="2ede0-118">此时[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="2ede0-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

   5. <span data-ttu-id="2ede0-119">在[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，选择 WCF Siebel。</span><span class="sxs-lookup"><span data-stu-id="2ede0-119">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select WCF-Siebel.</span></span> <span data-ttu-id="2ede0-120">选择的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装和 BizTalk 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="2ede0-120">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

      > [!IMPORTANT]
      >  <span data-ttu-id="2ede0-121">如果已有**Wcf-siebel**端口中配置的 BizTalk，请选择从端口**端口**列表。</span><span class="sxs-lookup"><span data-stu-id="2ede0-121">If you already have a **WCF-Siebel** port configured in BizTalk, select the port from the **Port** list.</span></span>  

   6. <span data-ttu-id="2ede0-122">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="2ede0-122">Click **Next**.</span></span>  

2. <span data-ttu-id="2ede0-123">从**选择绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="2ede0-123">From the **Select a binding** drop-down list, select **siebelBinding**, and then click **Configure**.</span></span>  

3. <span data-ttu-id="2ede0-124">在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**.</span><span class="sxs-lookup"><span data-stu-id="2ede0-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username**.</span></span>  

4. <span data-ttu-id="2ede0-125">指定的用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="2ede0-125">Specify the user name and password to connect to the Siebel system.</span></span>  

5. <span data-ttu-id="2ede0-126">单击**URI 属性**选项卡，并指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="2ede0-126">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="2ede0-127">有关详细信息的连接 URI 对于[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="2ede0-127">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="2ede0-128">如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。</span><span class="sxs-lookup"><span data-stu-id="2ede0-128">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="2ede0-129">但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。</span><span class="sxs-lookup"><span data-stu-id="2ede0-129">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  

6. <span data-ttu-id="2ede0-130">单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。</span><span class="sxs-lookup"><span data-stu-id="2ede0-130">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="2ede0-131">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="2ede0-131">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="2ede0-132">如果您正在生成元数据中使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]并且选择了现有 WCF Siebel 发送端口，不需要指定绑定属性。</span><span class="sxs-lookup"><span data-stu-id="2ede0-132">If you are generating metadata using [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] and you selected an existing WCF-Siebel send port, you need not specify the binding properties.</span></span> <span data-ttu-id="2ede0-133">绑定属性是从发送端口配置中选取。</span><span class="sxs-lookup"><span data-stu-id="2ede0-133">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="2ede0-134">但是，您可以选择指定如果任何，则需要在设计时的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="2ede0-134">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="2ede0-135">在这种情况下，将生成元数据时在设计时使用的绑定属性的新值。</span><span class="sxs-lookup"><span data-stu-id="2ede0-135">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="2ede0-136">但是，在运行时指定的发送端口配置中的绑定属性的值将适用。</span><span class="sxs-lookup"><span data-stu-id="2ede0-136">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

7. <span data-ttu-id="2ede0-137">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="2ede0-137">Click **OK**.</span></span>  

8. <span data-ttu-id="2ede0-138">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="2ede0-138">Click **Connect**.</span></span> <span data-ttu-id="2ede0-139">建立连接后，连接状态显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="2ede0-139">Once the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="2ede0-140">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="2ede0-140">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  

    <span data-ttu-id="2ede0-141">![使用适配器服务连接对话框](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span><span class="sxs-lookup"><span data-stu-id="2ede0-141">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span></span>  

    <span data-ttu-id="2ede0-142">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在 Siebel 系统执行各种操作的不同节点。</span><span class="sxs-lookup"><span data-stu-id="2ede0-142">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on the Siebel system.</span></span> <span data-ttu-id="2ede0-143">例如，**业务对象**节点包含所有的业务对象和可以在 Siebel 系统调用的业务组件。</span><span class="sxs-lookup"><span data-stu-id="2ede0-143">For example, the **Business Objects** node contains all the business objects and business components that can be invoked on the Siebel system.</span></span> <span data-ttu-id="2ede0-144">同样，**业务服务**节点连接到 Siebel 系统中包含所有业务服务。</span><span class="sxs-lookup"><span data-stu-id="2ede0-144">Similarly, the **Business Services**  node contains all the business services in the Siebel system you connected to.</span></span> <span data-ttu-id="2ede0-145">有关这些节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)。</span><span class="sxs-lookup"><span data-stu-id="2ede0-145">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span></span>