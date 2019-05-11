---
title: 使用适用于 SAP 的数据提供程序来创建报表服务器项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fe985b5-ba67-4179-a31c-4f41106c32be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45934085c75092f07264f8ed6fa4f9d6376ffbbb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372199"
---
# <a name="use-the-data-provider-for-sap-to-create-a-report-server-project"></a><span data-ttu-id="e1e98-102">使用适用于 SAP 的数据提供程序来创建报表服务器项目</span><span class="sxs-lookup"><span data-stu-id="e1e98-102">Use the Data Provider for SAP to Create a Report Server Project</span></span>
<span data-ttu-id="e1e98-103">必须创建报表服务器项目，使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，若要为 SAP 系统中可用的数据生成报表。</span><span class="sxs-lookup"><span data-stu-id="e1e98-103">You must create a Report Server project, using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], to generate reports for the data available in an SAP system.</span></span> <span data-ttu-id="e1e98-104">本主题将说明了如何创建报表服务器项目。</span><span class="sxs-lookup"><span data-stu-id="e1e98-104">This topic provides instructions on how to create a Report Server project.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e1e98-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="e1e98-105">Prerequisites</span></span>  
 <span data-ttu-id="e1e98-106">执行本主题中提供的过程之前，先确保已安装了[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]安装时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="e1e98-106">Before performing the procedures provided in this topic, make sure you installed the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] while installing the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation.</span></span> <span data-ttu-id="e1e98-107">有关详细信息[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，请参阅安装指南位于\<*安装驱动器*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。</span><span class="sxs-lookup"><span data-stu-id="e1e98-107">For more information about [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, refer to the installation guide available at \<*installation drive*\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
  
### <a name="to-create-a-report-server-project"></a><span data-ttu-id="e1e98-108">若要创建报表服务器项目</span><span class="sxs-lookup"><span data-stu-id="e1e98-108">To create a Report Server project</span></span>  
  
1. <span data-ttu-id="e1e98-109">启动[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并创建一个报表服务器项目。</span><span class="sxs-lookup"><span data-stu-id="e1e98-109">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create a Report Server project.</span></span> <span data-ttu-id="e1e98-110">若要创建报表服务器项目，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e1e98-110">To create a Report Server project, do the following:</span></span>  
  
   1.  <span data-ttu-id="e1e98-111">单击**文件**菜单上，单击**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="e1e98-111">Click the **File** menu, click **New**, and then click **Project**.</span></span>  
  
   2.  <span data-ttu-id="e1e98-112">在中**新的项目**对话框中，从**项目类型**列表中，选择**商业智能项目**。</span><span class="sxs-lookup"><span data-stu-id="e1e98-112">In the **New Project** dialog box, from the **Project types** list, select **Business Intelligence Projects**.</span></span> <span data-ttu-id="e1e98-113">从**Visual Studio 已安装的模板**列表中，选择**报表服务器项目**。</span><span class="sxs-lookup"><span data-stu-id="e1e98-113">From **the Visual Studio installed templates** list, select **Report Server Project**.</span></span>  
  
   3.  <span data-ttu-id="e1e98-114">指定的名称和项目的位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e1e98-114">Specify a name and location of the project and click **OK**.</span></span> <span data-ttu-id="e1e98-115">对于本主题中，指定作为项目的名称`SAP_ Report`。</span><span class="sxs-lookup"><span data-stu-id="e1e98-115">For this topic, specify the name of the project as `SAP_ Report`.</span></span>  
  
2. <span data-ttu-id="e1e98-116">添加新的数据源：</span><span class="sxs-lookup"><span data-stu-id="e1e98-116">Add a new data source:</span></span>  
  
   1. <span data-ttu-id="e1e98-117">在解决方案资源管理器，右键单击**共享数据源**，然后单击**添加新数据源**。</span><span class="sxs-lookup"><span data-stu-id="e1e98-117">From the Solution Explorer, right-click **Shared Data Sources**, and click **Add New Data Source**.</span></span>  
  
   2. <span data-ttu-id="e1e98-118">在中**共享数据源**对话框中**常规**选项卡上，指定数据源的名称。</span><span class="sxs-lookup"><span data-stu-id="e1e98-118">In the **Shared Data Source** dialog box, in the **General** tab, specify a name for the data source.</span></span> <span data-ttu-id="e1e98-119">有关本主题中，将名称指定为`SAPDataSource`。</span><span class="sxs-lookup"><span data-stu-id="e1e98-119">For this topic, specify the name as `SAPDataSource`.</span></span>  
  
   3. <span data-ttu-id="e1e98-120">从**类型**列表中，选择**SAP 数据提供程序**。</span><span class="sxs-lookup"><span data-stu-id="e1e98-120">From the **Type** list, select **Data Provider for SAP**.</span></span>  
  
   4. <span data-ttu-id="e1e98-121">在中**连接字符串**框中，指定的连接字符串[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e1e98-121">In the **Connection String** box, specify the connection string for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="e1e98-122">璝惠[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连接字符串，请参阅[了解数据提供程序类型适用于 SAP 连接字符串](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="e1e98-122">For information about the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
       <span data-ttu-id="e1e98-123">![创建数据源](../../adapters-and-accelerators/adapter-sap/media/8494c1a5-5e68-4178-a005-a6ea56d97ad7.gif "8494c1a5-5e68-4178-a005-a6ea56d97ad7")</span><span class="sxs-lookup"><span data-stu-id="e1e98-123">![Create a data source](../../adapters-and-accelerators/adapter-sap/media/8494c1a5-5e68-4178-a005-a6ea56d97ad7.gif "8494c1a5-5e68-4178-a005-a6ea56d97ad7")</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="e1e98-124">您可以选择指定的凭据作为连接字符串的一部分或下一步中所述指定它们。</span><span class="sxs-lookup"><span data-stu-id="e1e98-124">You can choose to specify the credentials as part of the connection string or specify them as described in the next step.</span></span>  
  
   5. <span data-ttu-id="e1e98-125">在中**凭据**选项卡上，选择下列选项之一，然后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="e1e98-125">In the **Credentials** tab, choose one of the following, and then click **OK**:</span></span>  
  
      |<span data-ttu-id="e1e98-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e1e98-126">Use this</span></span>|<span data-ttu-id="e1e98-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e1e98-127">To do this</span></span>|  
      |--------------|----------------|  
      |<span data-ttu-id="e1e98-128">**使用特定用户名和密码**</span><span class="sxs-lookup"><span data-stu-id="e1e98-128">**Use a specific user name and password**</span></span>|<span data-ttu-id="e1e98-129">指定用户名和密码以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="e1e98-129">Specify a user name and password to connect to the SAP system.</span></span>|  
      |<span data-ttu-id="e1e98-130">**提示输入凭据**</span><span class="sxs-lookup"><span data-stu-id="e1e98-130">**Prompt for credentials**</span></span>|<span data-ttu-id="e1e98-131">生成报表时，SAP 系统的输入的凭据。</span><span class="sxs-lookup"><span data-stu-id="e1e98-131">Enter the credentials for the SAP system while the report is generated.</span></span> <span data-ttu-id="e1e98-132">**注意：** 如果指定，作为连接字符串的一部分，此选项指定的凭据将覆盖凭据。</span><span class="sxs-lookup"><span data-stu-id="e1e98-132">**Note:**  The credentials you specify for this option will override the credentials, if specified, as part of the connection string.</span></span>|  
      |<span data-ttu-id="e1e98-133">**无凭据**</span><span class="sxs-lookup"><span data-stu-id="e1e98-133">**No credentials**</span></span>|<span data-ttu-id="e1e98-134">如果你要作为连接字符串的一部分提供的用户名和密码，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="e1e98-134">Choose this option if you are providing the user name and password as part of the connection string.</span></span>|  
  
      > [!NOTE]
      >  <span data-ttu-id="e1e98-135">报表服务器项目不支持 Windows 身份验证模式。</span><span class="sxs-lookup"><span data-stu-id="e1e98-135">The Windows Authentication mode is not supported for Report Server projects.</span></span>  
  
3. <span data-ttu-id="e1e98-136">添加新报表：</span><span class="sxs-lookup"><span data-stu-id="e1e98-136">Add a new report:</span></span>  
  
   1. <span data-ttu-id="e1e98-137">在解决方案资源管理器，右键单击**报表**，然后单击**添加新报表**。</span><span class="sxs-lookup"><span data-stu-id="e1e98-137">From the Solution Explorer, right-click **Reports**, and then click **Add New Report**.</span></span>  
  
       <span data-ttu-id="e1e98-138">这将启动报表向导。</span><span class="sxs-lookup"><span data-stu-id="e1e98-138">This starts the Report Wizard.</span></span>  
  
   2. <span data-ttu-id="e1e98-139">阅读欢迎屏幕上的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e1e98-139">Read the information on the welcome screen, and then click **Next**.</span></span>  
  
   3. <span data-ttu-id="e1e98-140">在中**选择数据源**对话框框中，选择**共享数据源**选项中，选择**SAPDataSource**您在上一步中创建，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e1e98-140">In the **Select the Data Source** dialog box, choose the **Shared data source** option, select the **SAPDataSource** you created in the previous step, and then click **Next**.</span></span>  
  
   4. <span data-ttu-id="e1e98-141">如果选择了**凭据提示**选项来创建数据源时指定的用户凭据**输入数据源凭据**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="e1e98-141">If you chose the **Prompt for credentials** option to specify the user credentials while creating the data source, an **Enter Data Source Credentials** dialog box appears.</span></span> <span data-ttu-id="e1e98-142">指定的用户名和密码以连接到 SAP 系统，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e1e98-142">Specify the user name and password to connect to the SAP system, and then click **OK**.</span></span>  
  
       <span data-ttu-id="e1e98-143">如果你选择用于指定凭据的任何其他选项，则向导将继续到下一步。</span><span class="sxs-lookup"><span data-stu-id="e1e98-143">If you chose any other option for specifying credentials, the wizard proceeds to the next step.</span></span>  
  
   5. <span data-ttu-id="e1e98-144">在中**设计查询**对话框框中，指定用于生成报表的查询字符串。</span><span class="sxs-lookup"><span data-stu-id="e1e98-144">In the **Design the Query** dialog box, specify a query string that is used to generate a report.</span></span> <span data-ttu-id="e1e98-145">例如：</span><span class="sxs-lookup"><span data-stu-id="e1e98-145">For example:</span></span>  
  
      ```  
      SELECT TOP 2 KUNNR, NAME1 FROM KNA1 WHERE NAME1 LIKE @PARAM  
      ```  
  
       <span data-ttu-id="e1e98-146">此查询将从 NAME1 其中是生成报表时将指定的名称 KNA1 表中检索前两个记录。</span><span class="sxs-lookup"><span data-stu-id="e1e98-146">This query will retrieve the top two records from the KNA1 table where the NAME1 is the name that you will specify while generating the report.</span></span>  
  
       <span data-ttu-id="e1e98-147">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="e1e98-147">Click **Next**.</span></span>  
  
   6. <span data-ttu-id="e1e98-148">在随后的对话框框中，您可以设计在其中你想要显示的报表的格式。</span><span class="sxs-lookup"><span data-stu-id="e1e98-148">In the subsequent dialog boxes you can design the format in which you want the report to appear.</span></span> <span data-ttu-id="e1e98-149">如果你想要使用的默认格式，请单击**完成 >>&#124;** 若要直接转到**完成**对话框。</span><span class="sxs-lookup"><span data-stu-id="e1e98-149">If you want to use the default format, click **Finish >>&#124;** to directly go to the **Finish** dialog box.</span></span>  
  
   7. <span data-ttu-id="e1e98-150">在中**完成向导**对话框中，指定报表的名称，查看摘要，，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="e1e98-150">In the **Completing the Wizard** dialog box, specify a name for the report, review the summary, and then click **Finish**.</span></span> <span data-ttu-id="e1e98-151">对于本主题中，指定作为报表的名称`SAPReport`。</span><span class="sxs-lookup"><span data-stu-id="e1e98-151">For this topic, specify the name of the report as `SAPReport`.</span></span>  
  
      <span data-ttu-id="e1e98-152">现在可以查看报表。</span><span class="sxs-lookup"><span data-stu-id="e1e98-152">You can now view the report.</span></span> <span data-ttu-id="e1e98-153">有关如何查看报表的说明，请参阅[查看适用于 SAP 报告](../../adapters-and-accelerators/adapter-sap/view-the-reports-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="e1e98-153">For instructions about how to view the report, see [view the Reports for SAP](../../adapters-and-accelerators/adapter-sap/view-the-reports-for-sap.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e98-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1e98-154">See Also</span></span>  
 [<span data-ttu-id="e1e98-155">使用包含 SSRS 的 SAP 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="e1e98-155">Use the Data Provider for SAP with SSRS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)