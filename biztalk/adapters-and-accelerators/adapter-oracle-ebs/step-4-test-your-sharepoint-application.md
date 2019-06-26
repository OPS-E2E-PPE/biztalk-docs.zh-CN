---
title: 步骤 4：测试 SharePoint 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a859044e-a28e-477e-a20b-f9bb3c9f7405
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ac732b009f25628651fae133e83acd7fcd5deb2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374544"
---
# <a name="step-4-test-your-sharepoint-application"></a>步骤 4：测试 SharePoint 应用程序
![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **若要完成的时间：** 10 分钟。  
  
 **目标：** 在 SharePoint 站点中添加 Web 部件并创建了应用程序后，必须通过从 Oracle E-business Suite 中检索一些数据来测试应用程序。 本主题将说明了如何使用应用程序来从 Oracle E-business Suite 中检索数据。  
  
## <a name="prerequisites"></a>先决条件  
 您将会创建包含相应的 Web 部件，以检索业务数据的 Web 部件页。 请参阅[步骤 3:创建 SharePoint 应用程序以从 Oracle E-business Suite 中检索数据](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)。  
  
### <a name="scenario-1-to-test-the-sharepoint-application-created-using-business-data-list-web-part"></a>应用场景 1：若要测试创建使用业务数据列表 Web 部件的 SharePoint 应用程序  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击的 SSP 在其下创建应用程序的名称。  
  
3.  在左窗格中，单击**查看所有网站内容**。 在右窗格中，单击**窗体模板**。  
  
4.  在中**窗体类别**列表中，单击**MS_SAMPLE_EMPLOYEE**。 在创建中的 Web 部件页时指定此名称[方案 1:使用业务数据列表 web 部件显示数据](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)。  
  
5.  搜索基于搜索字符串的员工。 例如，若要搜索的所有员工，请键入 **%** 在文本框中，单击**检索数据**。 下图显示了从 Oracle E-business Suite 中检索到的记录：  
  
     ![搜索结果](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")  
  
6.  您还可以通过输入其名字或姓氏搜索特定雇员：  
  
    -   若要使用第一个名称进行搜索，请键入后跟一个雇员的姓名首字母 **%** 符号以返回与搜索条件匹配的所有员工记录。  
  
    -   若要使用的最后一个名称进行搜索，请键入 **%** 跟员工的姓氏。  
  
    > [!NOTE]
    >  区分大小写的搜索字符串。  
  
     ![搜索按员工的名字](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")  
  
### <a name="scenario-2-to-test-the-sharepoint-application-created-to-perform-a-full-text-search"></a>应用场景 2：若要测试创建执行全文搜索的 SharePoint 应用程序  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击的 SSP 在其下创建应用程序的名称。  
  
3.  在左窗格中，单击**查看所有网站内容**。 在右窗格中，单击**窗体模板**。  
  
4.  在中**窗体类别**列表中，单击**MS_SAMPLE_EMPLOYEE_Search**。 在创建中的 Web 部件页时指定此名称[方案 2:执行搜索使用搜索框 Web 部件](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)在[方案 2:使用搜索框 Web 部件执行搜索](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)。  
  
5.  MS_SAMPLE_EMPLOYEE_Search 页将显示可在其中执行全文搜索 MS_SAMPLE EMPLOYEE 表的搜索框。 例如，如果你想要搜索的所有员工居住在纽约，键入`New York`在搜索框中，然后按 ENTER。  
  
     ![指定搜索参数](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34_Search_Result")  
  
6.  使用搜索结果将显示一个页面。 每个匹配的记录显示为搜索结果页中的链接。  
  
     ![搜索结果](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")  
  
7.  单击搜索结果以查看相应的员工记录中的链接。  
  
     ![详细雇员记录](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36_Search_Result2")  
  
## <a name="summary"></a>总结  
 在本教程中，您可以创建你想要从 SharePoint 门户网站访问的 Oracle E-business Suite 项目的 WCF 服务。 此外创建导入到 SharePoint 门户网站创建 Web 部件显示，并在 Oracle E-business Suite 中搜索数据的应用程序定义的 Oracle E-business Suite 项目。  
  
## <a name="see-also"></a>请参阅  
 [教程：从 SharePoint 站点上的 Oracle E-business Suite 的呈现数据](../../adapters-and-accelerators/adapter-oracle-ebs/tutorial-present-data-from-oracle-e-business-suite-on-a-sharepoint-site.md)