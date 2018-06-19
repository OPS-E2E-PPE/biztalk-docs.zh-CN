---
title: 步骤 4： 测试您的 SharePoint 应用程序 1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7ded5a5-88d5-40aa-814b-70bc0a7dcfa3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b8be51df02bd9796b41201c0495758c281e8f14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216629"
---
# <a name="step-4-test-your-sharepoint-application"></a>步骤 4： 测试 SharePoint 应用程序
![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 后您在 SharePoint 站点中添加 Web 部件，并且创建了应用程序，你必须通过从 SAP 系统中检索一些数据来测试应用程序。 本主题将说明了如何使用应用程序从 SAP 系统检索数据。  
  
## <a name="prerequisites"></a>先决条件  
  
-   您应已创建包含相应的 Web 部件，以检索业务数据的 Web 部件页。 请参阅[步骤 3： 创建 SharePoint 应用程序从 SAP 检索数据](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)。  
  
### <a name="to-test-the-sharepoint-application"></a>若要测试 SharePoint 应用程序  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击在其下创建应用程序的 SSP 的名称。  
  
3.  在左窗格中，单击**查看所有站点内容**。 在右窗格中，单击**表单模板**。  
  
4.  在**窗体类别**列表中，单击**Customer_SalesOrders**。 在创建 Web 部件页时指定此名称。 下图显示你创建的 Web 部件页。  
  
     ![已完成的 Web 部件页](../../adapters-and-accelerators/adapter-sap/media/3e9f22b1-8285-40f4-a67d-b51173c93671.gif "3e9f22b1-8285-40f4-a67d-b51173c93671")  
  
5.  搜索客户基于搜索字符串。 例如，搜索客户名称以"John E"开头。 为此：  
  
    1.  在客户列表部分中，从第一个列表中，单击**CustomerName**。  
  
    2.  从第二个列表中，单击**开头**。  
  
    3.  在文本框中，键入**John E**。  
  
    4.  单击**检索数据**链接或按 ENTER。 下图显示从 SAP 系统中检索满足搜索条件的记录。  
  
         ![从 SAP 系统搜索的结果](../../adapters-and-accelerators/adapter-sap/media/c97e9e2c-0908-46af-9a54-8a4354847c47.gif "c97e9e2c-0908-46af-9a54-8a4354847c47")  
  
6.  你现在可以看到在列表中的任何客户的详细信息和销售订单与客户，如果任何相关联。 若要执行此操作，请单击针对客户编号选项按钮。 刷新该页面提供了详细信息和相应的 Web 部件中特定客户的销售订单。  
  
     ![显示在 SharePoint 上的 SAP 数据](../../adapters-and-accelerators/adapter-sap/media/29fc4a9e-facd-4455-bcfe-5f4d866b2dc7.gif "29fc4a9e-facd-4455-bcfe-5f4d866b2dc7")  
  
     如果未正确显示客户和关联的销售订单的详细信息，您已成功完成本教程。 如果没有或不正确的数据将显示，请仔细检查您的工作以确保正确执行所有任务。  
  
## <a name="summary"></a>摘要  
 在本教程中，你将创建你想要从 SharePoint 门户网站访问的 SAP 项目的 WCF 服务。 你还创建导入 SharePoint 门户网站创建 Web 部件显示从 SAP 系统的数据应用程序定义的 SAP 项目。  
  
## <a name="see-also"></a>另请参阅  
 [教程 1： 从 SharePoint 站点上的 SAP 系统提供数据](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)