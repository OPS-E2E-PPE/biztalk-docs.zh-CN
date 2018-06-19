---
title: 步骤 5 （在本地）： 生成插入消息 inito SalesOrder 表的架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab0bc1a7-8bcd-4110-88e6-4eddf0b57068
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: facb5d638ed82e1632e434a2a9c9063a2c3daa68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279317"
---
# <a name="step-5-on-premises-generate-the-schema-for-inserting-a-message-inito-salesorder-table"></a><span data-ttu-id="e7adc-102">步骤 5 （在本地）： 生成插入消息 inito SalesOrder 表的架构</span><span class="sxs-lookup"><span data-stu-id="e7adc-102">Step 5 (On Premises): Generate the Schema for Inserting a Message inito SalesOrder Table</span></span>
<span data-ttu-id="e7adc-103">必须根据业务方案中，插入的 X12 销售订单消息从 Contoso 发送到 Northwind 的**SalesOrder**表如果订购的数量大于 100。</span><span class="sxs-lookup"><span data-stu-id="e7adc-103">According to the business scenario, the X12 sales order message sent from Contoso must be inserted into Northwind’s **SalesOrder** table if the quantity ordered is greater than 100.</span></span> <span data-ttu-id="e7adc-104">若要插入到消息**SalesOrder**表，必须生成的架构**插入**表上的操作。</span><span class="sxs-lookup"><span data-stu-id="e7adc-104">To insert a message into a **SalesOrder** table, you must generate the schema for the **Insert** operation on the table.</span></span> <span data-ttu-id="e7adc-105">在本主题中，你将创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，，然后使用[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]生成用于执行架构**插入**操作**SalesOrder**表。</span><span class="sxs-lookup"><span data-stu-id="e7adc-105">In this topic, you will create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution, and then use the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] to generate the schema for performing an **Insert** operation on the **SalesOrder** table.</span></span>  
  
### <a name="to-generate-the-schema-for-insert-operation-on-salesorder-table"></a><span data-ttu-id="e7adc-106">生成用于在 SalesOrder 表中执行插入操作的架构</span><span class="sxs-lookup"><span data-stu-id="e7adc-106">To generate the schema for Insert operation on SalesOrder table</span></span>  
  
1.  <span data-ttu-id="e7adc-107">创建一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Visual Studio 项目。</span><span class="sxs-lookup"><span data-stu-id="e7adc-107">Create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Visual Studio project.</span></span> <span data-ttu-id="e7adc-108">从 Visual Studio**文件**菜单上，单击**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="e7adc-108">From the Visual Studio **File** menu, click **New**, and then click **Project**.</span></span> <span data-ttu-id="e7adc-109">在**新项目**对话框中，从已安装模板列表中单击**BizTalk 项目**，然后选择**空[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目**。</span><span class="sxs-lookup"><span data-stu-id="e7adc-109">In the **New Project** dialog box, from the list of installed templates, click **BizTalk Projects**, and then select **Empty [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Project**.</span></span> <span data-ttu-id="e7adc-110">项目名称输入`OrderProcessingDemo`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e7adc-110">For the project name enter `OrderProcessingDemo` and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="e7adc-111">右键单击解决方案资源管理器中的项目名称，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="e7adc-111">Right-click the project name in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="e7adc-112">在**添加生成的项**对话框中，选择**使用适配器服务**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="e7adc-112">In the **Add Generated Items** dialog box, select **Consume Adapter Service**, and then click **Add**.</span></span> <span data-ttu-id="e7adc-113">此时[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]会打开。</span><span class="sxs-lookup"><span data-stu-id="e7adc-113">The [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="e7adc-114">从**选择的绑定**下拉列表中，选择**sqlBinding**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="e7adc-114">From the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="e7adc-115">在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表中，执行下列其中一项：</span><span class="sxs-lookup"><span data-stu-id="e7adc-115">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential  type** drop-down list, do one of the following:</span></span>  
  
    |<span data-ttu-id="e7adc-116">单击此链接</span><span class="sxs-lookup"><span data-stu-id="e7adc-116">Click this</span></span>|<span data-ttu-id="e7adc-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e7adc-117">To do this</span></span>|  
    |----------------|----------------|  
    |<span data-ttu-id="e7adc-118">**无**</span><span class="sxs-lookup"><span data-stu-id="e7adc-118">**None**</span></span>|<span data-ttu-id="e7adc-119">使用 Windows 身份验证连接至 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="e7adc-119">Connect to SQL Server using Windows authentication.</span></span>|  
    |<span data-ttu-id="e7adc-120">**Windows**</span><span class="sxs-lookup"><span data-stu-id="e7adc-120">**Windows**</span></span>|<span data-ttu-id="e7adc-121">使用 Windows 身份验证连接至 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="e7adc-121">Connect to SQL Server using Windows authentication.</span></span>|  
    |<span data-ttu-id="e7adc-122">**用户名**</span><span class="sxs-lookup"><span data-stu-id="e7adc-122">**Username**</span></span>|<span data-ttu-id="e7adc-123">通过指定 SQL Server 数据库中定义的用户凭据，指定用于连接 SQL Server 的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="e7adc-123">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="e7adc-124">请注意，用户名和密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e7adc-124">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="e7adc-125">**注意：** 如果你离开**用户名**和**密码**为空白字段，该适配器将连接到 SQL Server 使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="e7adc-125">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span>|  
  
6.  <span data-ttu-id="e7adc-126">单击**URI 属性**选项卡上，然后指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="e7adc-126">Click the **URI Properties** tab, and then specify values for the connection parameters.</span></span> <span data-ttu-id="e7adc-127">有关连接 URI 的详细信息为[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，请参阅[SQL Server 连接 URI](http://msdn.microsoft.com/library/dd788089.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e7adc-127">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], see [SQL Server Connection URI](http://msdn.microsoft.com/library/dd788089.aspx).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7adc-128">如果连接参数包含任何保留的字符，则必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。</span><span class="sxs-lookup"><span data-stu-id="e7adc-128">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="e7adc-129">但是，如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。</span><span class="sxs-lookup"><span data-stu-id="e7adc-129">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7adc-130">如果不在“URI 属性”选项卡中指定任何值，[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]会将 URI 设置为 `mssql://.//`。</span><span class="sxs-lookup"><span data-stu-id="e7adc-130">If you do not specify any values in the URI property tab, the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] puts the URI as `mssql://.//`.</span></span> <span data-ttu-id="e7adc-131">在此类情况下，适配器将连接至本地计算机上的默认数据库和默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="e7adc-131">In such a case, the adapter connects to the default database and the default database instance on the local computer.</span></span>  
  
7.  <span data-ttu-id="e7adc-132">在**配置适配器**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e7adc-132">In the **Configure Adapter** dialog box, click **OK**.</span></span> <span data-ttu-id="e7adc-133">在**使用适配器服务**对话框中，单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="e7adc-133">In the **Consume Adapter Service** dialog box, click **Connect**.</span></span>  
  
8.  <span data-ttu-id="e7adc-134">从**选择类别**框中，展开**表**，然后单击**SalesOrder**表。</span><span class="sxs-lookup"><span data-stu-id="e7adc-134">From the **Select a category** box, expand **Tables**, and then click the **SalesOrder** table.</span></span>  
  
9. <span data-ttu-id="e7adc-135">从**可用类别和操作**框中，选择**插入**，单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e7adc-135">From the **Available categories and operations** box, select **Insert**, click **Add**, and then click **OK**.</span></span> <span data-ttu-id="e7adc-136">新项将添加至解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="e7adc-136">New items are added to the Solution Explorer.</span></span> <span data-ttu-id="e7adc-137">架构文件 (**TableOperation.dbo.SalesOrder.xsd**) 是对其执行插入操作生成的架构**SalesOrder**表。</span><span class="sxs-lookup"><span data-stu-id="e7adc-137">The schema file (**TableOperation.dbo.SalesOrder.xsd**) is the generated schema for performing an Insert operation on the **SalesOrder** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7adc-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7adc-138">See Also</span></span>  
 [<span data-ttu-id="e7adc-139">教程 4： 创建使用 BizTalk Server 2013 的混合应用程序</span><span class="sxs-lookup"><span data-stu-id="e7adc-139">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)