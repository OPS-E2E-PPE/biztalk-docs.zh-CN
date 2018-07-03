---
title: 连接到 Siebel 系统中 Visual Studio 中使用使用适配器服务外接程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2baaa361-1b14-4d00-bcef-f68bc3fa7139
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9916dc1328412428e4f21858905a005e35d9d1d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013814"
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-consume-adapter-service-add-in"></a><span data-ttu-id="0e4d6-102">连接到 Siebel 系统中 Visual Studio 中使用使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="0e4d6-102">Connect to the Siebel System in Visual Studio Using Consume Adapter Service Add-in</span></span>
<span data-ttu-id="0e4d6-103">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]安装时安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-103">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] is installed when you install [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="0e4d6-104">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]加载在计算机上安装的所有 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-104">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] loads all the WCF-Custom bindings installed on the computer.</span></span> <span data-ttu-id="0e4d6-105">若要连接到使用基于 WCF 的 Siebel 系统[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在 BizTalk 项目中，必须使用**siebelBinding**。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-105">To connect to a Siebel system using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in a BizTalk project, you must use the **siebelBinding**.</span></span>  

## <a name="connecting-to-a-siebel-system-using-consume-adapter-service-add-in"></a><span data-ttu-id="0e4d6-106">连接到 Siebel 系统使用使用适配器服务外接程序</span><span class="sxs-lookup"><span data-stu-id="0e4d6-106">Connecting to a Siebel System Using Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="0e4d6-107">执行以下步骤连接到 Siebel 系统[!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-107">Perform the following steps to connect to a Siebel system using the [!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)].</span></span>  

#### <a name="to-connect-to-a-siebel-system"></a><span data-ttu-id="0e4d6-108">若要连接到 Siebel 系统</span><span class="sxs-lookup"><span data-stu-id="0e4d6-108">To connect to a Siebel system</span></span>  

1. <span data-ttu-id="0e4d6-109">若要使用连接[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="0e4d6-109">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="0e4d6-110">创建 BizTalk 项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-110">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

   2. <span data-ttu-id="0e4d6-111">右键单击解决方案资源管理器中的项目，指向**外**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-111">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   3. <span data-ttu-id="0e4d6-112">在中**添加生成的项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0e4d6-112">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="0e4d6-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0e4d6-113">Use this</span></span>    |             <span data-ttu-id="0e4d6-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0e4d6-114">To do this</span></span>             |
      |----------------|------------------------------------|
      | <span data-ttu-id="0e4d6-115">**类别**</span><span class="sxs-lookup"><span data-stu-id="0e4d6-115">**Categories**</span></span> | <span data-ttu-id="0e4d6-116">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-116">Click **Consume Adapter Service**.</span></span> |
      | <span data-ttu-id="0e4d6-117">**模板**</span><span class="sxs-lookup"><span data-stu-id="0e4d6-117">**Templates**</span></span>  | <span data-ttu-id="0e4d6-118">单击**使用适配器服务**。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-118">Click **Consume Adapter Service**.</span></span> |


   4. <span data-ttu-id="0e4d6-119">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-119">Click **Add**.</span></span> <span data-ttu-id="0e4d6-120">此时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-120">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] opens.</span></span>  

2. <span data-ttu-id="0e4d6-121">从**选择绑定**下拉列表中，选择**siebelBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-121">From the **Select a binding** drop-down list, select **siebelBinding**, and then click **Configure**.</span></span>  

3. <span data-ttu-id="0e4d6-122">在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**.</span><span class="sxs-lookup"><span data-stu-id="0e4d6-122">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username**.</span></span>  

4. <span data-ttu-id="0e4d6-123">指定的用户名和密码以连接到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-123">Specify the user name and password to connect to the Siebel system.</span></span>  

5. <span data-ttu-id="0e4d6-124">单击**URI 属性**选项卡，并指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-124">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="0e4d6-125">有关详细信息的连接 URI 对于[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-125">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="0e4d6-126">如果连接参数包含任何保留的字符，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-126">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="0e4d6-127">但是，如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-127">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  

6. <span data-ttu-id="0e4d6-128">单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-128">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="0e4d6-129">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-129">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

7. <span data-ttu-id="0e4d6-130">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-130">Click **OK**.</span></span>  

8. <span data-ttu-id="0e4d6-131">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-131">Click **Connect**.</span></span> <span data-ttu-id="0e4d6-132">建立连接后，连接状态显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-132">Once the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="0e4d6-133">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-133">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  

    <span data-ttu-id="0e4d6-134">![使用适配器服务连接对话框](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span><span class="sxs-lookup"><span data-stu-id="0e4d6-134">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span></span>  

    <span data-ttu-id="0e4d6-135">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]显示包含可以在 Siebel 系统执行各种操作的不同节点。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-135">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on the Siebel system.</span></span> <span data-ttu-id="0e4d6-136">例如，**业务对象**节点包含所有的业务对象和可以在 Siebel 系统调用的业务组件。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-136">For example, the **Business Objects** node contains all the business objects and business components that can be invoked on the Siebel system.</span></span> <span data-ttu-id="0e4d6-137">同样，**业务服务**节点连接到 Siebel 系统中包含所有业务服务。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-137">Similarly, the **Business Services**  node contains all the business services in the Siebel system you connected to.</span></span> <span data-ttu-id="0e4d6-138">有关这些节点的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-138">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span></span>