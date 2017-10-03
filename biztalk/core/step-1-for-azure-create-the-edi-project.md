---
title: "（适用于 Azure) 中的步骤 1： 创建 EDI 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d353129-04f0-456b-b371-b346959f5155
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb5f2e7af54ef99acff37a350c5fa7d9ba65af5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-for-azure-create-the-edi-project"></a><span data-ttu-id="85227-102">（适用于 Azure) 中的步骤 1： 创建 EDI 项目</span><span class="sxs-lookup"><span data-stu-id="85227-102">Step 1 (For Azure): Create the EDI Project</span></span>
<span data-ttu-id="85227-103">在本部分中，Contoso 将使用 [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] 2012 年 4 月版本创建一个 EDI 项目。</span><span class="sxs-lookup"><span data-stu-id="85227-103">In this section, Contoso creates an EDI project using the [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] April 2012 release.</span></span> <span data-ttu-id="85227-104">在此项目中，Contoso 将添加以下内容：</span><span class="sxs-lookup"><span data-stu-id="85227-104">As part of the project, Contoso adds the following:</span></span>  
  
-   <span data-ttu-id="85227-105">内部的销售订单架构 (**ECommerceSalesOrder.xsd**) 到 X12 840 EDI 销售订单架构会进行转换。</span><span class="sxs-lookup"><span data-stu-id="85227-105">An internal sales order schema (**ECommerceSalesOrder.xsd**) to which the X12 840 EDI sales order schema will be transformed.</span></span> <span data-ttu-id="85227-106">在消息被接收到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中之后，Contoso 将使用内部架构处理消息</span><span class="sxs-lookup"><span data-stu-id="85227-106">Contoso uses the internal schema to process the message after it is received into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="85227-107">转换 (**EDI840TOSALESORDER。TRFM**) 将 X12 840 销售订单架构**ECommerceSalesOrder**架构。</span><span class="sxs-lookup"><span data-stu-id="85227-107">A transform (**EDI840TOSALESORDER.TRFM**) to convert the X12 840 sales order schema to the **ECommerceSalesOrder** schema.</span></span>  
  
 <span data-ttu-id="85227-108">在 [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] 的 Azure BizTalk 门户中创建协议时，Contoso 会使用这些项目。</span><span class="sxs-lookup"><span data-stu-id="85227-108">Contoso uses these artifacts while creating an agreement in the Azure BizTalk portal in [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)].</span></span>  
  
### <a name="to-create-edi-project"></a><span data-ttu-id="85227-109">创建 EDI 项目</span><span class="sxs-lookup"><span data-stu-id="85227-109">To create EDI project</span></span>  
  
1.  <span data-ttu-id="85227-110">打开[!INCLUDE[vs2010](../includes/vs2010-md.md)]，从**文件**菜单中的指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="85227-110">Open [!INCLUDE[vs2010](../includes/vs2010-md.md)], from the **File** menu point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="85227-111">在**新项目**对话框中，从**已安装的模板**，选择**Service Bus**。</span><span class="sxs-lookup"><span data-stu-id="85227-111">In the **New Project** dialog box, from the **Installed Templates**, select **Service Bus**.</span></span> <span data-ttu-id="85227-112">指定项目名称以及该项目的位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="85227-112">Specify a project name and a location for the project, and then click **OK**.</span></span>  
  
##  <span data-ttu-id="85227-113"><a name="BKMK_CreateSchema"></a>若要创建在 EDI 项目架构</span><span class="sxs-lookup"><span data-stu-id="85227-113"><a name="BKMK_CreateSchema"></a> To create a schema within the EDI project</span></span>  
  
1.  <span data-ttu-id="85227-114">从解决方案资源管理器，右键单击你刚刚创建的项目名称，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="85227-114">From the Solution Explorer, right-click the project name you just created, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="85227-115">在**添加新项**对话框中，从**已安装的模板**，选择**架构**，指定的名称作为架构**ECommerceSalesOrder.xsd**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="85227-115">In the **Add New Item** dialog box, from the **Installed Templates**, select **Schema**, specify the name of the schema as **ECommerceSalesOrder.xsd**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="85227-116">编辑并生成类似如下的架构：</span><span class="sxs-lookup"><span data-stu-id="85227-116">Edit and build the schema to resemble the following:</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-16"?>  
    \<xs:schema xmlns="http://ECommerceSalesOrder.Inbound" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://ECommerceSalesOrder.Inbound" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
      \<xs:element name="SalesOrder">  
        \<xs:complexType>  
          \<xs:sequence>  
            \<xs:element name="CompanyCode" type="xs:string" />  
            \<xs:element name="PartID" type="xs:int" />  
            \<xs:element name="Quantity" type="xs:int" />  
            \<xs:element name="AskPrice" type="xs:decimal" />  
            \<xs:element name="RequestShipmentDate" type="xs:date" />  
            \<xs:element name="Address">  
              \<xs:complexType>  
                \<xs:sequence>  
                  \<xs:element name="Line1" type="xs:string" />  
                  \<xs:element name="Line2" type="xs:string" />  
                  \<xs:element name="City" type="xs:string" />  
                  \<xs:element name="State" type="xs:string" />  
                  \<xs:element name="Country" type="xs:string" />  
                  \<xs:element name="Zipcode" type="xs:int" />  
                \</xs:sequence>  
              \</xs:complexType>  
            \</xs:element>  
            \<xs:element name="Contact">  
              \<xs:complexType>  
                \<xs:sequence>  
                  \<xs:element name="Firstname" type="xs:string" />  
                  \<xs:element name="Lastname" type="xs:string" />  
                \</xs:sequence>  
              \</xs:complexType>  
            \</xs:element>  
            \<xs:element name="Comments" type="xs:string" />  
            \<xs:element name="DateNow" type="xs:date" />  
          \</xs:sequence>  
        \</xs:complexType>  
      \</xs:element>  
    \</xs:schema>  
    ```  
  
     <span data-ttu-id="85227-117">可以使用架构编辑器生成此架构。</span><span class="sxs-lookup"><span data-stu-id="85227-117">You can use the Schema Editor to build this schema.</span></span> <span data-ttu-id="85227-118">有关详细信息，请参阅[使用 BizTalk 编辑器](../core/using-biztalk-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="85227-118">For more information, see [Using BizTalk Editor](../core/using-biztalk-editor.md).</span></span>  
  
4.  <span data-ttu-id="85227-119">保存该架构。</span><span class="sxs-lookup"><span data-stu-id="85227-119">Save the schema.</span></span>  
  
##  <span data-ttu-id="85227-120"><a name="BKMK_CreateTrfm"></a>若要创建 EDI 项目中转换</span><span class="sxs-lookup"><span data-stu-id="85227-120"><a name="BKMK_CreateTrfm"></a> To create a transform within the EDI project</span></span>  
  
1.  <span data-ttu-id="85227-121">从解决方案资源管理器，右键单击你刚刚创建的项目名称，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="85227-121">From the Solution Explorer, right-click the project name you just created, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="85227-122">在**添加新项**对话框中，从**已安装的模板**，选择**映射**，指定的名称作为架构**Edi840ToSalesOrder.trfm**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="85227-122">In the **Add New Item** dialog box, from the **Installed Templates**, select **Map**, specify the name of the schema as **Edi840ToSalesOrder.trfm**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="85227-123">在映射中，对于源架构选择**X12_00401_840.xsd**。</span><span class="sxs-lookup"><span data-stu-id="85227-123">In the map, for the source schema select **X12_00401_840.xsd**.</span></span> <span data-ttu-id="85227-124">这是用于 EDI 销售订单的标准 X12 架构。</span><span class="sxs-lookup"><span data-stu-id="85227-124">This is the standard X12 schema for an EDI sales order.</span></span> <span data-ttu-id="85227-125">必须已将此架构添加到创建的 EDI 项目中。</span><span class="sxs-lookup"><span data-stu-id="85227-125">You must have already added this schema to the EDI project you created.</span></span> <span data-ttu-id="85227-126">你可以下载此示例和其他 X12 架构从[http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)。</span><span class="sxs-lookup"><span data-stu-id="85227-126">You can download this, and other X12 schemas from [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057).</span></span> <span data-ttu-id="85227-127">X12 架构属于**MicrosoftEdiXSDTemplates.zip**从下载位置可用的包。</span><span class="sxs-lookup"><span data-stu-id="85227-127">The X12 schemas are part of the **MicrosoftEdiXSDTemplates.zip** package available from the download location.</span></span>  
  
4.  <span data-ttu-id="85227-128">对于目标架构中，选择**ECommerceSalesOrder.xsd**。</span><span class="sxs-lookup"><span data-stu-id="85227-128">For the destination schema, select **ECommerceSalesOrder.xsd**.</span></span> <span data-ttu-id="85227-129">你在本主题前面的内容中已创建此架构。</span><span class="sxs-lookup"><span data-stu-id="85227-129">You created this schema earlier in this topic.</span></span>  
  
5.  <span data-ttu-id="85227-130">通过连接源和目标架构中的相关节点来创建映射。</span><span class="sxs-lookup"><span data-stu-id="85227-130">Create the map by connecting the relevant nodes in the source and target schemas.</span></span>  
  
6.  <span data-ttu-id="85227-131">保存映射。</span><span class="sxs-lookup"><span data-stu-id="85227-131">Save the map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85227-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85227-132">See Also</span></span>  
 [<span data-ttu-id="85227-133">教程 4： 创建使用 BizTalk Server 2013 的混合应用程序</span><span class="sxs-lookup"><span data-stu-id="85227-133">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)