---
title: "步骤 4： 测试 SharePoint 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a859044e-a28e-477e-a20b-f9bb3c9f7405
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 427235d27e4e783111ccdb60f799c228737cd008
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-your-sharepoint-application"></a>步骤 4： 测试 SharePoint 应用程序
![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **完成时间：** 10 分钟  
  
 **目标：**后您在 SharePoint 站点中添加 Web 部件，并且创建了应用程序，你必须通过从 Oracle E-business Suite 检索某些数据测试应用程序。 本主题将说明了如何使用应用程序从 Oracle E-business Suite 检索数据。  
  
## <a name="prerequisites"></a>先决条件  
 您应已创建包含相应的 Web 部件，以检索业务数据的 Web 部件页。 请参阅[步骤 3： 创建 SharePoint 应用程序从 Oracle E-business Suite 检索数据](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)。  
  
### <a name="scenario-1-to-test-the-sharepoint-application-created-using-business-data-list-web-part"></a>方案 1： 测试 SharePoint 应用程序创建使用业务数据列表 Web 部件  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击在其下创建应用程序的 SSP 的名称。  
  
3.  在左窗格中，单击**查看所有站点内容**。 在右窗格中，单击**表单模板**。  
  
4.  在**窗体类别**列表中，单击**MS_SAMPLE_EMPLOYEE**。 创建中的 Web 部件页时指定此名称[方案 1： 使用业务数据列表 web 部件显示数据](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)。  
  
5.  搜索员工基于搜索字符串。 例如，若要搜索的所有员工，请键入 **%** 文本框中，然后单击**检索数据**。 下图显示从 Oracle E-business Suite 中检索的记录：  
  
     ![搜索结果](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")  
  
6.  您还可以通过输入其名字或姓氏搜索特定雇员：  
  
    -   若要搜索使用第一个名称，请键入后跟雇员姓名首字母 **%** 符号返回的搜索条件匹配的所有雇员的记录。  
  
    -   若要搜索使用最后一个名称，键入 **%** 跟员工的姓氏。  
  
    > [!NOTE]
    >  区分大小写的搜索字符串。  
  
     ![员工的名字按搜索](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")  
  
### <a name="scenario-2-to-test-the-sharepoint-application-created-to-perform-a-full-text-search"></a>方案 2： 测试 SharePoint 应用程序创建来执行全文搜索  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击在其下创建应用程序的 SSP 的名称。  
  
3.  在左窗格中，单击**查看所有站点内容**。 在右窗格中，单击**表单模板**。  
  
4.  在**窗体类别**列表中，单击**MS_SAMPLE_EMPLOYEE_Search**。 创建中的 Web 部件页时指定此名称[方案 2： 使用搜索框 Web 部件执行搜索](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)中[方案 2： 使用搜索框 Web 部件执行搜索](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)。  
  
5.  MS_SAMPLE_EMPLOYEE_Search 页面显示搜索框中在你可以执行 MS_SAMPLE 员工表的全文搜索。 例如，如果你想要搜索的位于纽约的所有员工，键入`New York`搜索框中，然后按 enter 键。  
  
     ![指定的搜索参数](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34_Search_Result")  
  
6.  使用的搜索结果将显示一个页面。 每个匹配的记录显示为搜索结果页中的链接。  
  
     ![搜索结果](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")  
  
7.  单击以查看相应的员工记录的搜索结果中的链接。  
  
     ![详细的员工记录](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36_Search_Result2")  
  
## <a name="summary"></a>摘要  
 在本教程中，你将创建你想要从 SharePoint 门户网站访问 Oracle E-business Suite 项目的 WCF 服务。 你还创建导入 SharePoint 门户网站创建 Web 部件，为在 Oracle E-business Suite 中搜索数据和呈现应用程序定义的 Oracle E-business Suite 项目。  
  
## <a name="see-also"></a>另请参阅  
 [教程： 从 SharePoint 站点上的 Oracle E-business Suite 显示数据](../../adapters-and-accelerators/adapter-oracle-ebs/tutorial-present-data-from-oracle-e-business-suite-on-a-sharepoint-site.md)