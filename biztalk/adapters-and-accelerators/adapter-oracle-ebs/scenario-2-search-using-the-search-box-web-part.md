---
title: 方案 2： 搜索使用搜索框 web 部件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a233772f-7577-4ac5-b55a-cb1ba2f464c7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03e536df00499e8965632a3952eb3ae50e3f83df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218541"
---
# <a name="scenario-2--search-using-the-search-box-web-part"></a>方案 2： 搜索使用搜索框 web 部件
我们将在 Microsoft Office SharePoint Server，若要配置使用可以对执行全文搜索的搜索应用程序配置的搜索设置中 Oracle E-business Suite 的 MS_SAMPLE_EMPLOYEE 接口表。 更高版本，我们将添加一个搜索框 Web 部件到从可在其中进行搜索。  
  
 
  
##  <a name="Define"></a>定义内容的源  
 本部分介绍的定义从 Microsoft Office SharePoint Server 可对数据爬网的内容源。 这涉及到将内容映射到 Id 的枚举器中创建方法实例[步骤 2： 创建应用程序定义文件的 Oracle E-business Suite 项目](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)。  
  
#### <a name="to-define-a-content-source"></a>若要定义内容的源  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击名称的共享服务提供程序 (SSP) 想要配置的搜索应用程序。  
  
3.  在主页上，在**搜索**部分中，单击**搜索设置**。  
  
4.  在配置搜索设置页上的下的左窗格中，**爬网**，单击**默认内容访问帐户**以指定要用作默认帐户，爬网内容时的帐户。  
  
5.  在默认内容访问帐户页上，指定用户名和密码凭据，然后单击**确定**。 您将返回到搜索管理页。  
  
6.  在左窗格中下**爬网**，单击**内容源**。  
  
7.  在管理内容源页中，单击**新内容源**。  
  
8.  在管理内容源页中，单击**新内容源**。  
  
9. 在添加内容源页上：  
  
    1.  类型`MS_SAMPLE_EMPLOYEE`中**名称**框。  
  
    2.  在**内容的源类型**区域中，单击**业务数据**。  
  
    3.  在**应用程序**区域中，单击**爬网所选应用程序**，然后选择**MS_SAMPLE_EMPLOYEE_Instance**复选框。  
  
    4.  在**启动完全爬网**区域中，选择**启动完全爬网的此内容的源**复选框，并依次**确定**。  
  
         ![添加内容的源](../../adapters-and-accelerators/adapter-oracle-ebs/media/27-add-content-source.gif "27_Add_Content_Source")  
  
10. 您将与新添加的内容源返回到管理内容源页。 内容的源将通过在 Oracle E-business Suite MS_SAMPLE_EMPLOYEE 接口表中的数据进行爬网。 等待，直到完成爬网。  
  
11. 在左窗格中下**爬网**，单击**爬网日志**，然后验证日志文件，以确保爬网成功。  
  
##  <a name="Scope"></a>定义已爬网内容的作用域  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击名称的共享服务提供程序 (SSP) 想要配置的搜索应用程序。  
  
3.  在主页上，在**搜索**部分中，单击**搜索设置**。  
  
4.  在配置搜索设置页上的下的左窗格中，**查询和结果**，单击**作用域**若要定义对数据爬网的作用域。  
  
5.  在视图作用域页上，单击**新作用域**。  
  
6.  在创建作用域页上，键入`MS_SAMPLE_EMPLOYEE_Search`中**标题**框中，并依次**确定**。  
  
     ![创建一个作用域](../../adapters-and-accelerators/adapter-oracle-ebs/media/28-create-scope.gif "28_Create_Scope")  
  
7.  将返回与新的作用域添加到视图作用域页。 在**更新状态**在新添加的作用域中的列中，单击**添加规则**链接。  
  
8.  在添加作用域规则页上：  
  
    1.  在**作用域规则类型**区域中，单击**内容源**。  
  
    2.  在**内容源**列表中，单击**MS_SAMPLE_EMPLOYEE**，然后单击**确定**。  
  
         ![添加作用域规则](../../adapters-and-accelerators/adapter-oracle-ebs/media/29-add-scope-rule.gif "29_Add_Scope_Rule")  
  
9. 您将返回到视图作用域页上添加为作用域的规则。 在左窗格中，单击**搜索管理**。  
  
10. 在搜索管理页上找到**需要更新的范围**行，然后单击**立即启动更新**链接。  
  
 **范围更新状态**行将显示范围更新的状态。 等待，直到已完成更新。 更新完成后，范围是可供使用。  
  
##  <a name="AddScope"></a>将范围添加到搜索下拉列表中  
 创建搜索范围后，必须将作用域添加到 Microsoft Office SharePoint Server 中的搜索下拉列表，以便可以使用它。  
  
#### <a name="to-add-the-scope-to-the-search-dropdown"></a>若要将作用域添加到搜索下拉列表中  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击名称的共享服务提供程序 (SSP) 想要配置的搜索应用程序。  
  
3.  在共享服务管理页上，在右上角，单击**站点操作**，然后单击**站点设置**。  
  
4.  在站点设置页上，在**网站集管理**部分中，单击**搜索作用域**。  
  
5.  在视图作用域页上，单击**搜索下拉列表中**链接。  
  
     ![查看作用域](../../adapters-and-accelerators/adapter-oracle-ebs/media/30-view-scope.gif "30_View_Scope")  
  
6.  在编辑范围显示组页上：  
  
    1.  在**作用域**区域中，选择**MS_SAMPLE_EMPLOYEE_Search**复选框。  
  
    2.  在**默认作用域**区域中，单击**MS_SAMPLE_EMPLOYEE_Search**中**默认作用域**列表，，然后单击**确定**。  
  
         ![编辑范围显示组页](../../adapters-and-accelerators/adapter-oracle-ebs/media/31-edit-scope-display-group.gif "31_Edit_Scope_Display_Group")  
  
7.  将返回与 MS_SAMPLE_EMPLOYEE_Search 范围中的搜索下拉列表中显示组添加到视图作用域页。  
  
##  <a name="SearchWebPart"></a>添加搜索框 Web 部件  
 若要使用户能够执行全文搜索中 Oracle E-business Suite 的 MS_SAMPLE_EMPLOYEE 接口表，现在必须创建 Web 部件页，并将搜索框 Web 部件添加到它。  
  
#### <a name="to-add-the-search-box-web-part"></a>若要添加搜索框 Web 部件  
  
1.  创建调用的 Web 部件页**MS_SAMPLE_EMPLOYEE_Search**。 若要了解有关创建的 Web 部件页的步骤，请参阅[方案 1： 使用业务数据列表 web 部件显示数据](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)中[方案 1： 使用业务数据列表 web 部件显示数据](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)。  
  
2.  在 MS_SAMPLE_EMPLOYEE_Search 页上，单击**添加 Web 部件**。  
  
3.  在**添加 Web 部件**对话框中，在**搜索**部分中，选择**搜索框**复选框，并依次**添加**。  
  
     ![添加搜索框 Web 部件](../../adapters-and-accelerators/adapter-oracle-ebs/media/32-search-web-part.gif "32_Search_Web_Part")  
  
4.  搜索框 Web 部件添加到 MS_SAMPLE_EMPLOYEE_Search 页面。  
  
     ![搜索框 Web 部件](../../adapters-and-accelerators/adapter-oracle-ebs/media/33-search-web-part-final.gif "33_Search_Web_Part_Final")  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 创建 SharePoint 应用程序从 Oracle E-business Suite 检索数据](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)  
 [方案 1： 使用业务数据列表 web 部件的显示数据](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)