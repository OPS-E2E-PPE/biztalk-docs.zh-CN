---
title: 步骤 3：创建要从 Oracle E-business Suite 中检索数据的 SharePoint 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eaa16011-9284-4ccf-8132-9c1e14cc6aa7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baaaa68a372900304ec9a776a49f46e0623d71cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374547"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-e-business-suite"></a>步骤 3：创建 SharePoint 应用程序以从 Oracle E-business Suite 中检索数据
![步骤 3，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **若要完成的时间：** 15 分钟  
  
 **目标：** 现在，必须导入的应用程序定义文件中 Microsoft Office SharePoint Server，并设置应用程序来从 Oracle E-business Suite 中检索数据。  
  
## <a name="prerequisites"></a>先决条件  
  
-   您将会创建应用程序定义文件中所述[步骤 2:为 Oracle E-business Suite 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)。  
  
-   必须运行 Microsoft 单一登录服务。  
  
 
  
##  <a name="SSO"></a> 在 SharePoint 中创建的 SSO 应用程序  
 若要从 SharePoint 应用程序访问 Oracle E-business Suite 中的数据，必须设置映射到 Oracle E-business Suite 的用户的 SharePoint 用户的 SSO 应用程序。 在 SharePoint 中创建的 SSO 应用程序涉及以下步骤：  
  
1.  **管理服务器上单一登录设置**。 在此步骤中，你指定的用户帐户，可以管理和设置单一登录服务。 可以在管理服务器设置页上执行操作。 此选项可从 SharePoint 中心管理控制台。 有关此步骤的详细信息，请参阅"配置单一登录适用于 Office SharePoint Server 2007"部分在[ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291)。  
  
2.  **管理企业应用程序定义的设置**。 在此步骤中，您配置企业应用程序定义的设置。 您可以从企业应用程序定义页的管理设置执行操作。 此选项可从 SharePoint 中心管理控制台。  
  
    1.  在管理中心内，在顶部导航栏上，单击**操作**。  
  
    2.  在操作页中**的安全配置**部分中，单击**管理的单一登录设置**。  
  
    3.  在单一登录页上，管理设置中**企业应用程序定义设置**部分中，单击**管理企业应用程序定义的设置**。  
  
    4.  在管理企业应用程序定义页上，提供的值**显示名称**，**应用程序名称**，并**联系人电子邮件地址**字段。  
  
        > [!IMPORTANT]
        >  有关**应用程序名称**字段中，请确保指定相同的 SSO 应用程序名称为指定**SecondarySsoApplicationId**时创建应用程序定义文件中，为变量中所述[步骤 2:为 Oracle E-business Suite 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)。  
  
    5.  将其他字段保留为默认值，然后单击**确定**。  
  
3.  **管理企业应用程序定义的帐户信息**。 在此步骤中，启用单个用户或组从 SharePoint 连接到企业应用程序。 从根本上来说，在此步骤中您映射单个用户或组到用户在 LOB 系统。 您还指定用于连接到 LOB 系统的凭据。 您可以从企业应用程序定义页的管理帐户信息执行操作。 此选项可从 SharePoint 中心管理控制台。 有关此步骤的详细信息，请参阅"管理企业应用程序定义的帐户信息"部分在[ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291)。  
  
##  <a name="SSP"></a> 创建共享的服务提供程序  
 共享服务提供程序是共享的服务和及其支持资源的逻辑分组。 可以使用 SharePoint 中心管理控制台来创建 SSP。  
  
 必须定义网站时创建 ssp。 请记住的端口号和你创建的站点地址。 你将导出到此站点的业务数据目录应用程序定义。  
  
 有关创建 SSP 的详细信息，请参阅"一章概述：创建和配置共享服务提供程序"处[ http://go.microsoft.com/fwlink/?LinkId=105119 ](http://go.microsoft.com/fwlink/?LinkId=105119)。  
  
##  <a name="Import"></a> 导入应用程序定义文件  
 现在必须将应用程序定义文件导入 ssp。  
  
#### <a name="to-import-the-application-definition-file"></a>若要导入应用程序定义文件  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击你想要导入应用程序定义的 SSP 的名称。  
  
3.  在中**业务数据目录**部分中，单击**导入应用程序定义**。  
  
4.  在导入应用程序定义页，此时会打开，浏览到 Employee.xml，选择该文件，并单击**打开**。  
  
5.  单击“导入” 。  
  
6.  已成功导入应用程序定义文件后，单击**确定**。  
  
     由于导入应用程序定义文件，MS_SAMPLE_EMPLOYEE，而创建的应用程序将显示。  
  
     ![在 SharePoint 中的应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/media/b0695720-0113-49dc-8eb6-c685aceada6c.gif "b0695720-0113-49dc-8eb6-c685aceada6c")  
  
## <a name="next-steps"></a>后续步骤  
 现在，已准备好创建 Web 部件，用于创建 SharePoint 站点查看和搜索将从 Oracle E-business Suite 中提取的业务数据。 我们将创建一个：  
  
-   业务数据列表 Web 部件显示 MS_SAMPLE_EMPLOYEE 接口表中的员工记录。 请参阅[方案 1:使用业务数据列表 Web 部件显示数据](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)。  
  
-   搜索框 Web 部件上 MS_SAMPLE_EMPLOYEE 接口表执行全文搜索。 请参阅[方案 2:使用搜索框 Web 部件进行搜索](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程：从 SharePoint 站点上的 Oracle E-business Suite 中显示数据](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)