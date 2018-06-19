---
title: 查看适用于 SAP 的报表 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0932ffc5-cde0-4d14-822f-713b760c3f12
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d446a24ca9432842d52062acb494f92060bbaaf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218213"
---
# <a name="view-the-reports-for-sap"></a><span data-ttu-id="39c59-102">查看适用于 SAP 的报表</span><span class="sxs-lookup"><span data-stu-id="39c59-102">View the Reports for SAP</span></span>
<span data-ttu-id="39c59-103">创建报表后，可以查看使用 Visual Studio 或通过网络上 Internet Information Services (IIS) 和访问的报表服务器上托管它。</span><span class="sxs-lookup"><span data-stu-id="39c59-103">After you have created the report, you can view it either using Visual Studio or host it on the Report Server on Internet Information Services (IIS) and access over the network.</span></span> <span data-ttu-id="39c59-104">本主题提供有关如何查看报表同时在 Visual Studio 和使用 IIS 的说明。</span><span class="sxs-lookup"><span data-stu-id="39c59-104">This topic provides instructions on how to view reports both in Visual Studio and using IIS.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="39c59-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="39c59-105">Prerequisites</span></span>  
 <span data-ttu-id="39c59-106">执行本主题中提供过程之前，你必须已生成报表中所述[SAP 数据提供程序用于创建报表服务器项目](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)。</span><span class="sxs-lookup"><span data-stu-id="39c59-106">Before performing the procedures provided in this topic, you must have generated a report as described in [Use the Data Provider for SAP to Create a Report Server Project](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md).</span></span>  
  
### <a name="to-view-the-reports-in-visual-studio"></a><span data-ttu-id="39c59-107">在 Visual Studio 中查看报表</span><span class="sxs-lookup"><span data-stu-id="39c59-107">To view the reports in Visual Studio</span></span>  
  
1.  <span data-ttu-id="39c59-108">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，右键单击解决方案资源管理器中的项目名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="39c59-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], right-click the project name in the Solution Explorer, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="39c59-109">在报表属性页对话框中，单击**Configuration Manager**，然后清除下的复选框**部署**列。</span><span class="sxs-lookup"><span data-stu-id="39c59-109">In the report property pages dialog box, click **Configuration Manager**, and clear the check box under the **Deploy** column.</span></span> <span data-ttu-id="39c59-110">单击 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="39c59-110">Click **Close**.</span></span>  
  
3.  <span data-ttu-id="39c59-111">在报表属性页对话框中，为**StartItem**属性，选择报表的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="39c59-111">In the report property pages dialog box, for the **StartItem** property, select the name of the report, and then click **OK**.</span></span>  
  
     <span data-ttu-id="39c59-112">![指定报表服务器项目的属性](../../adapters-and-accelerators/adapter-sap/media/b3c500f7-840d-461f-945c-66db239d81b9.gif "b3c500f7-840d-461f-945c-66db239d81b9")</span><span class="sxs-lookup"><span data-stu-id="39c59-112">![Specify properties for the Report Server project](../../adapters-and-accelerators/adapter-sap/media/b3c500f7-840d-461f-945c-66db239d81b9.gif "b3c500f7-840d-461f-945c-66db239d81b9")</span></span>  
  
4.  <span data-ttu-id="39c59-113">右键单击解决方案资源管理器中的项目名称，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="39c59-113">Right-click the project name in the Solution Explorer, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="39c59-114">按`F5`以运行该项目生成报表。</span><span class="sxs-lookup"><span data-stu-id="39c59-114">Press `F5` to run the project to generate the report.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="39c59-115">在[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]，您可以通过单击查看报表**预览**选项卡。在这种情况下，将在预览选项卡中打开后续的对话框。</span><span class="sxs-lookup"><span data-stu-id="39c59-115">In [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)], you can see the report by clicking the **Preview** tab. In such a case, the subsequent dialog boxes will open within the preview tab.</span></span>  
  
6.  <span data-ttu-id="39c59-116">可打开一个对话框以及与你为报表指定相同的名称。</span><span class="sxs-lookup"><span data-stu-id="39c59-116">A dialog box with the same name as you specified for the report opens up.</span></span> <span data-ttu-id="39c59-117">如果你选择创建数据源时**提示输入凭据**选项，为 SAP 系统中，输入用户名和密码，然后单击**查看报表**。</span><span class="sxs-lookup"><span data-stu-id="39c59-117">While creating the data source, if you chose the **Prompt for credentials** option, enter the user name and password for the SAP system, and then click **View Report**.</span></span>  
  
     <span data-ttu-id="39c59-118">![指定要生成报告的 SAP 凭据](../../adapters-and-accelerators/adapter-sap/media/fa831aae-b2d1-4ba2-a23f-f7beeb8f898e.gif "fa831aae-b2d1-4ba2-a23f-f7beeb8f898e")</span><span class="sxs-lookup"><span data-stu-id="39c59-118">![Specify SAP credentials to generate a report](../../adapters-and-accelerators/adapter-sap/media/fa831aae-b2d1-4ba2-a23f-f7beeb8f898e.gif "fa831aae-b2d1-4ba2-a23f-f7beeb8f898e")</span></span>  
  
7.  <span data-ttu-id="39c59-119">如果你指定查询时创建报表服务器项目需要参数，你必须输入参数的值。</span><span class="sxs-lookup"><span data-stu-id="39c59-119">If the query you specified while creating the Report Server project requires a parameter, you must enter the value of the parameter.</span></span> <span data-ttu-id="39c59-120">例如，查询中指定[SAP 数据提供程序用于创建报表服务器项目](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)主题中，需要你指定的参数，参数的值。</span><span class="sxs-lookup"><span data-stu-id="39c59-120">For example, for the query you specified in the [Use the Data Provider for SAP to Create a Report Server Project](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md) topic, requires you to specify a value for the parameter, PARAM.</span></span>  
  
     <span data-ttu-id="39c59-121">如果需要，指定的参数的值，然后单击**查看报表**。</span><span class="sxs-lookup"><span data-stu-id="39c59-121">Specify the value of the parameter, if required, and click **View Report**.</span></span>  
  
     <span data-ttu-id="39c59-122">![指定要生成一个报表参数](../../adapters-and-accelerators/adapter-sap/media/5deec152-771b-46b4-84da-dd176193d7f3.gif "5deec152-771b-46b4-84da-dd176193d7f3")</span><span class="sxs-lookup"><span data-stu-id="39c59-122">![Specify parameters to generate a report](../../adapters-and-accelerators/adapter-sap/media/5deec152-771b-46b4-84da-dd176193d7f3.gif "5deec152-771b-46b4-84da-dd176193d7f3")</span></span>  
  
### <a name="to-host-the-reports-on-report-server"></a><span data-ttu-id="39c59-123">若要承载报表服务器上的报告</span><span class="sxs-lookup"><span data-stu-id="39c59-123">To host the reports on Report Server</span></span>  
  
1.  <span data-ttu-id="39c59-124">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，右键单击解决方案资源管理器中的项目名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="39c59-124">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], right-click the project name in the Solution Explorer, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="39c59-125">在报表属性页对话框中，单击**Configuration Manager**，然后选择下的复选框**部署**列。</span><span class="sxs-lookup"><span data-stu-id="39c59-125">In the report property pages dialog box, click **Configuration Manager**, and select the check box under the **Deploy** column.</span></span> <span data-ttu-id="39c59-126">单击 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="39c59-126">Click **Close**.</span></span>  
  
3.  <span data-ttu-id="39c59-127">在报表属性页对话框中，为**StartItem**属性，选择报表的名称。</span><span class="sxs-lookup"><span data-stu-id="39c59-127">In the report property pages dialog box, for the **StartItem** property, select the name of the report.</span></span>  
  
4.  <span data-ttu-id="39c59-128">在报表属性页对话框中，为**TargetServerURL**属性，对于报表服务器中，指定 URL，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="39c59-128">In the report property pages dialog box, for the **TargetServerURL** property, specify a URL for the Report Server, and then click **OK**.</span></span> <span data-ttu-id="39c59-129">例如：</span><span class="sxs-lookup"><span data-stu-id="39c59-129">For example:</span></span>  
  
    ```  
    http://localhost/reportserver  
    ```  
  
     <span data-ttu-id="39c59-130">![指定的报表服务器 URL](../../adapters-and-accelerators/adapter-sap/media/397ddfd6-f3d2-4327-9bc3-1efa22dc2249.gif "397ddfd6-f3d2-4327-9bc3-1efa22dc2249")</span><span class="sxs-lookup"><span data-stu-id="39c59-130">![Specify URL for the Report Server](../../adapters-and-accelerators/adapter-sap/media/397ddfd6-f3d2-4327-9bc3-1efa22dc2249.gif "397ddfd6-f3d2-4327-9bc3-1efa22dc2249")</span></span>  
  
5.  <span data-ttu-id="39c59-131">右键单击解决方案资源管理器中的项目名称，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="39c59-131">Right-click the project name in the Solution Explorer, and then click **Build**.</span></span>  
  
6.  <span data-ttu-id="39c59-132">右键单击解决方案资源管理器中的项目名称，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="39c59-132">Right-click the project name in the Solution Explorer, and then click **Deploy**.</span></span>  
  
7.  <span data-ttu-id="39c59-133">启动 IIS。</span><span class="sxs-lookup"><span data-stu-id="39c59-133">Start IIS.</span></span> <span data-ttu-id="39c59-134">单击**启动**，单击**运行**，类型`inetmgr`，按`Enter`。</span><span class="sxs-lookup"><span data-stu-id="39c59-134">Click **Start**, click **Run**, type `inetmgr`, and press `Enter`.</span></span>  
  
8.  <span data-ttu-id="39c59-135">在**Internet Information Services (IIS) Manager**管理单元中，展开计算机名称，展开**网站**，展开**Default Web Site**，右键单击**ReportServer**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="39c59-135">In the **Internet Information Services (IIS) Manager** snap-in, expand the computer name, expand **Web Sites**, expand **Default Web Site**, right-click **ReportServer**, and then click **Browse**.</span></span>  
  
9. <span data-ttu-id="39c59-136">在右窗格中，单击该项目的名称，然后单击上的报表的名称。</span><span class="sxs-lookup"><span data-stu-id="39c59-136">In the right pane, click the name of the project, and then click on the name of the report.</span></span>  
  
10. <span data-ttu-id="39c59-137">如果你选择创建数据源时**提示输入凭据**选项、 SAP 系统中输入的用户名和密码，然后单击**查看报表**。</span><span class="sxs-lookup"><span data-stu-id="39c59-137">While creating the data source, if you chose the **Prompt for credentials** option, enter the user name and password for the SAP system and click **View Report**.</span></span>  
  
11. <span data-ttu-id="39c59-138">如果你指定查询时创建报表服务器项目需要参数，你必须输入参数的值。</span><span class="sxs-lookup"><span data-stu-id="39c59-138">If the query you specified while creating the Report Server project requires a parameter, you must enter the value of the parameter.</span></span> <span data-ttu-id="39c59-139">例如，查询中指定[SAP 数据提供程序用于创建报表服务器项目](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)主题中，需要你指定的参数，参数的值。</span><span class="sxs-lookup"><span data-stu-id="39c59-139">For example, for the query you specified in the [Use the Data Provider for SAP to Create a Report Server Project](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md) topic, requires you to specify a value for the parameter, PARAM.</span></span>  
  
     <span data-ttu-id="39c59-140">如果需要，指定的参数的值，然后单击**查看报表**。</span><span class="sxs-lookup"><span data-stu-id="39c59-140">Specify the value of the parameter, if required, and click **View Report**.</span></span>  
  
     <span data-ttu-id="39c59-141">![指定要生成一个报表参数](../../adapters-and-accelerators/adapter-sap/media/221c8c12-4e4f-47f5-9289-9e9212cf6e25.gif "221c8c12-4e4f-47f5-9289-9e9212cf6e25")</span><span class="sxs-lookup"><span data-stu-id="39c59-141">![Specify parameters to generate a report](../../adapters-and-accelerators/adapter-sap/media/221c8c12-4e4f-47f5-9289-9e9212cf6e25.gif "221c8c12-4e4f-47f5-9289-9e9212cf6e25")</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="39c59-142">你还可以通过给报表的 URL 查看直接从 web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="39c59-142">You can also view directly from the web browser by giving the URL for the report.</span></span> <span data-ttu-id="39c59-143">报表的典型 URL `is http://localhohost/reportserver/<report_name>`。</span><span class="sxs-lookup"><span data-stu-id="39c59-143">A typical URL for the report `is http://localhohost/reportserver/<report_name>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c59-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39c59-144">See Also</span></span>  
 [<span data-ttu-id="39c59-145">适用于 SAP 的 SSRS 使用的数据提供程序</span><span class="sxs-lookup"><span data-stu-id="39c59-145">Use the Data Provider for SAP with SSRS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)