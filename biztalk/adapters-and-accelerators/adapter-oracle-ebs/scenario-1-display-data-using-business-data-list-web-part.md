---
title: 应用场景 1：使用业务数据列表 web 部件显示数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3831814-8b70-4352-b22f-cebd08750ef5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2a88c99c6b0386a621a9ecdf44d901312736254
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374649"
---
# <a name="scenario-1-display-data-using-business-data-list-web-part"></a>应用场景 1：使用业务数据列表 web 部件显示数据
我们将使用**业务数据列表**适用于 Web 部件**Finder**方法实例。 此 Web 部件，可指定要从 Oracle E-business Suite 中检索员工的列表的搜索表达式。 对于本教程中，这被称为显示员工 Web 部件。 本部分介绍如何创建此 Web 部件。 有关创建 Web 部件的详细信息，请参阅"自定义业务数据列表、 Web 部件和站点"网址[ http://go.microsoft.com/fwlink/?LinkId=104131 ](http://go.microsoft.com/fwlink/?LinkId=104131)。  
  
 必须添加 Web 部件之前创建的 Web 部件页。  
  
## <a name="creating-a-web-part-page"></a>创建 Web 部件页  
 本部分介绍如何创建 Web 部件页。  
  
###  <a name="WebPart"></a> 若要创建的 Web 部件页  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**。  
  
2.  在左侧的导航窗格中，单击你想要导入应用程序定义的 SSP 的名称。  
  
3.  在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。  
  
     ![若要创建 web 部件的菜单](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4.  在创建页上，在**网页**部分中，单击**Web 部件页**。  
  
5.  在新的 Web 部件页上，执行以下步骤：  
  
    1.  在中**名称**字段中，键入页面的名称。 对于本教程中，键入作为名称**MS_SAMPLE_EMPLOYEE**。  
  
    2.  选择**如果文件已存在，则覆盖**复选框，如果你想要使用相同的名称创建新的页覆盖旧页面。  
  
    3.  在中**布局**部分中，从**选择一个布局模板**框中，选择适用于 Web 部件页的布局。 对于本教程中，选择**整页、 垂直**。  
  
    4.  在中**保存位置**部分中，在**文档库**列表中，单击**窗体模板**。  
  
    5.  单击 **“创建”**。 在创建后下, 图显示 Web 部件页。  
  
         ![新的 web 部件页](../../adapters-and-accelerators/adapter-oracle-ebs/media/23-web-part.gif "23_Web_Part")  
  
    6.  您现在必须将 Web 部件添加到此页。  
  
## <a name="adding-a-business-data-list-web-part"></a>添加业务数据列表 Web 部件  
 现在，你必须将业务数据列表 Web 部件添加到 Web 部件页。 使用此 Web 部件将来自 MS_SAMPLE_EMPLOYEE 接口表相匹配的搜索表达式 Oracle E-business Suite 中检索员工记录的列表。 此 Web 部件对应于**Finder**方法实例 (*Finder_Instance*) 创建在 Business Data Catalog Definition Editor。  
  
#### <a name="to-add-a-business-data-list-web-part"></a>若要添加业务数据列表 Web 部件  
  
1.  在 MS_SAMPLE_EMPLOYEE 页上，单击**添加 Web 部件**。  
  
2.  在中**添加 Web 部件**对话框中**业务数据**部分中，选择**业务数据列表**复选框，然后依次**添加**。  
  
     ![创建业务数据 Web 部件的选项](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  在新添加的业务数据列表 Web 部件，单击**打开工具窗格**链接。  
  
     ![Web 部件中打开工具窗格](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  业务数据列表工具窗格将在右窗格中打开。 在中**业务数据列表**部分中，对于**类型**字段中，单击**浏览**按钮。  
  
     ![业务数据列表工具窗格](../../adapters-and-accelerators/adapter-oracle-ebs/media/24-bdc-browse.gif "24_BDC_Browse")  
  
5.  在中**业务数据类型选取器**对话框中，选择**MS_SAMPLE_EMPLOYEE_Instance**应用程序，，然后单击**确定**。  
  
     ![选择应用程序实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/25-bdc-picker.gif "25_BDC_Picker")  
  
6.  展开**外观**节点，然后在**标题**框中，键入 Web 部件的标题。 为此 Web 部件中，键入**员工列表**。  
  
7.  在业务数据列表工具窗格中，单击**Apply**，然后单击**确定**。 业务数据列表 Web 部件现在看起来如下所示：  
  
     ![业务数据列表 Web 部件](../../adapters-and-accelerators/adapter-oracle-ebs/media/26-bdc-webpart.gif "26_BDC_WebPart")  
  
8.  Web 部件列出了通过执行 MS_SAMPLE_EMPLOYEE 接口表上的选择操作返回的字段。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：创建 SharePoint 应用程序以从 Oracle E-business Suite 中检索数据](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)   
 [方案 2：使用搜索框 Web 部件进行搜索](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)