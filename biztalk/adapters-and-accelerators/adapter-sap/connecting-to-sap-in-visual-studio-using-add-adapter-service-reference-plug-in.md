---
title: "Visual Studio 中使用连接到 SAP 添加适配器服务引用插件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05116c2f-08a4-495b-a031-d377e7ca33e0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31436f7835aa940b86289ae3c80c276f95e0f105
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="connecting-to-sap-in-visual-studio-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="eca9a-102">Visual Studio 中使用连接到 SAP 添加插件的适配器服务引用</span><span class="sxs-lookup"><span data-stu-id="eca9a-102">Connecting to SAP in Visual Studio Using Add Adapter Service Reference Plug-in</span></span>
<span data-ttu-id="eca9a-103">若要连接到 SAP 系统使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在.NET 编程解决方案中，你必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="eca9a-103">To connect to an SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in a .NET programming solution, you must use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="eca9a-104">本主题将说明了如何使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="eca9a-104">This topic provides instructions on how to use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="connecting-to-an-sap-system-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="eca9a-105">连接到 SAP 系统使用适配器将服务引用添加插件</span><span class="sxs-lookup"><span data-stu-id="eca9a-105">Connecting to an SAP System Using Add Adapter Service Reference Plug-in</span></span>  
 <span data-ttu-id="eca9a-106">执行以下步骤以连接到 SAP 系统使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="eca9a-106">Perform the following steps to connect to an SAP system using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
#### <a name="to-connect-to-an-sap-system"></a><span data-ttu-id="eca9a-107">若要连接到 SAP 系统</span><span class="sxs-lookup"><span data-stu-id="eca9a-107">To connect to an SAP system</span></span>  
  
1.  <span data-ttu-id="eca9a-108">若要使用连接[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]BizTalk 解决方案中：</span><span class="sxs-lookup"><span data-stu-id="eca9a-108">To connect using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="eca9a-109">中创建一个项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="eca9a-109">Create a project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="eca9a-110">右键单击解决方案资源管理器中的项目，然后单击**添加适配器服务引用**。</span><span class="sxs-lookup"><span data-stu-id="eca9a-110">Right-click the project in Solution Explorer, and then click **Add Adapter Service Reference**.</span></span> <span data-ttu-id="eca9a-111">此时[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="eca9a-111">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] opens.</span></span>  
  
2.  <span data-ttu-id="eca9a-112">从**选择的绑定**下拉列表中，选择**sapBinding**单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="eca9a-112">From the **Select a binding** drop-down list, select **sapBinding** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="eca9a-113">在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="eca9a-113">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="eca9a-114">如果你使用 SAP 安全网络连接 (SNC) 库连接到 SAP 系统，则不指定用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="eca9a-114">If you are using the SAP Secure Network Connection (SNC) library to connect to an SAP system, do not specify a username and password.</span></span>  
  
4.  <span data-ttu-id="eca9a-115">单击**URI 属性**选项卡上，并指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="eca9a-115">Click the **URI Properties** tab and specify values for the connection parameters.</span></span> <span data-ttu-id="eca9a-116">有关连接 URI 的详细信息为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="eca9a-116">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="eca9a-117">如果你使用 SAP SNC 库连接到 SAP 系统，设置**UseSnc**连接属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="eca9a-117">If you are using the SAP SNC library to connect to an SAP system, set the **UseSnc** connection property to **True**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eca9a-118">如果连接参数包含任何保留的字符，则必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。</span><span class="sxs-lookup"><span data-stu-id="eca9a-118">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="eca9a-119">但是，如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。</span><span class="sxs-lookup"><span data-stu-id="eca9a-119">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
5.  <span data-ttu-id="eca9a-120">单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。</span><span class="sxs-lookup"><span data-stu-id="eca9a-120">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="eca9a-121">例如，如果你想要针对 ReceiveIdoc 操作则必须设置**ReceiveIdocFormat**将属性绑定到字符串。</span><span class="sxs-lookup"><span data-stu-id="eca9a-121">For example, if you want to target a ReceiveIdoc operation you must set the **ReceiveIdocFormat** binding property to String.</span></span> <span data-ttu-id="eca9a-122">有关绑定属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="eca9a-122">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="eca9a-123">如果你使用 SAP SNC 库连接到 SAP 系统，设置**SncLibrary**和**SncPartnerName**为适当的值。</span><span class="sxs-lookup"><span data-stu-id="eca9a-123">If you are using the SAP SNC library to connect to an SAP system, set the **SncLibrary** and **SncPartnerName** to appropriate values.</span></span>  
    >   
    >  <span data-ttu-id="eca9a-124">**SncLibrary**绑定属性采用的路径以及使用 SNC 连接到 SAP 系统所需的 Dll 的文件名。</span><span class="sxs-lookup"><span data-stu-id="eca9a-124">The **SncLibrary** binding property takes the path and the filename of the DLLs required for using SNC to connect to an SAP system.</span></span> <span data-ttu-id="eca9a-125">这些 Dll 必须存在 SAP 客户端计算机上和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="eca9a-125">These DLLs must be present on the computer with the SAP client and [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] installed.</span></span> <span data-ttu-id="eca9a-126">有关详细信息请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南位于\<安装指南\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。</span><span class="sxs-lookup"><span data-stu-id="eca9a-126">For more information see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide available at \<installation guide\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
    >   
    >  <span data-ttu-id="eca9a-127">**SncPartnerName**绑定属性将通信合作伙伴的 SNC 名称。</span><span class="sxs-lookup"><span data-stu-id="eca9a-127">The **SncPartnerName** binding property takes the SNC name of the communication partner.</span></span>  
  
6.  <span data-ttu-id="eca9a-128">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eca9a-128">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="eca9a-129">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="eca9a-129">Click **Connect**.</span></span> <span data-ttu-id="eca9a-130">建立连接后，连接状态将显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="eca9a-130">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="eca9a-131">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="eca9a-131">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span> <span data-ttu-id="eca9a-132">图形用户界面是适用于[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="eca9a-132">The graphical user interface is same for the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
     <span data-ttu-id="eca9a-133">![使用适配器服务连接的对话框](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span><span class="sxs-lookup"><span data-stu-id="eca9a-133">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span></span>  
  
     <span data-ttu-id="eca9a-134">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]显示包含可以在某个 SAP 系统中调用的各种项目的不同节点。</span><span class="sxs-lookup"><span data-stu-id="eca9a-134">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] displays different nodes containing various artifacts that can be invoked in an SAP system.</span></span> <span data-ttu-id="eca9a-135">例如， **RFC**节点包含在连接到 SAP 系统中可用的所有 Rfc。</span><span class="sxs-lookup"><span data-stu-id="eca9a-135">For example, the **RFC** node contains all the RFCs available in the SAP system you connected to.</span></span> <span data-ttu-id="eca9a-136">有关这些节点的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。</span><span class="sxs-lookup"><span data-stu-id="eca9a-136">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca9a-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eca9a-137">See Also</span></span>  
 [<span data-ttu-id="eca9a-138">在 Visual Studio 中连接到 SAP 系统</span><span class="sxs-lookup"><span data-stu-id="eca9a-138">Connect to the SAP System in Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)