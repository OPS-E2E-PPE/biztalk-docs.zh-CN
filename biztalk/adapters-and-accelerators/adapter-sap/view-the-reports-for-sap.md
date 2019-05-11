---
title: 查看适用于 SAP 的报表 |Microsoft Docs
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
ms.openlocfilehash: 49f43b35eacd264820afd07fce9d218a28e6b2e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372028"
---
# <a name="view-the-reports-for-sap"></a>查看适用于 SAP 的报表
创建报表后，可以查看使用 Visual Studio 或通过网络将其托管在 Internet 信息服务 (IIS) 和访问上的报表服务器上。 本主题提供有关如何查看报表，在 Visual Studio 和使用 IIS 中的说明。  
  
## <a name="prerequisites"></a>先决条件  
 执行本主题中提供的过程之前，你必须生成一个报表中所述[SAP 数据提供程序用于创建报表服务器项目](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)。  
  
### <a name="to-view-the-reports-in-visual-studio"></a>在 Visual Studio 中查看报表  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，右键单击解决方案资源管理器中的项目名称，然后单击**属性**。  
  
2. 在报表属性页对话框中，单击**Configuration Manager**，并清除下的复选框**部署**列。 单击 **“关闭”**。  
  
3. 在报表属性页对话框中，对于**StartItem**属性中，选择报表的名称，然后单击**确定**。  
  
    ![指定报表服务器项目属性](../../adapters-and-accelerators/adapter-sap/media/b3c500f7-840d-461f-945c-66db239d81b9.gif "b3c500f7-840d-461f-945c-66db239d81b9")  
  
4. 右键单击解决方案资源管理器中的项目名称，然后单击**生成**。  
  
5. 按`F5`运行此项目以生成报表。  
  
   > [!IMPORTANT]
   >  在中[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]，可以通过单击查看报表**预览**选项卡。在这种情况下，后续对话框将打开预览选项卡内。  
  
6. 打开一个对话框，使用与你为报表指定相同的名称。 如果选择了创建数据源时**凭据提示**选项，为 SAP 系统中，输入用户名和密码，然后单击**查看报告**。  
  
    ![指定 SAP 凭据以生成报表](../../adapters-and-accelerators/adapter-sap/media/fa831aae-b2d1-4ba2-a23f-f7beeb8f898e.gif "fa831aae-b2d1-4ba2-a23f-f7beeb8f898e")  
  
7. 如果指定了查询您创建报表服务器项目需要的参数时，必须输入参数的值。 例如，查询中指定[SAP 数据提供程序用于创建报表服务器项目](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)主题中，需要指定参数，参数的值。  
  
    如果需要，指定参数的值，然后单击**查看报表**。  
  
    ![指定用于生成报表的参数](../../adapters-and-accelerators/adapter-sap/media/5deec152-771b-46b4-84da-dd176193d7f3.gif "5deec152-771b-46b4-84da-dd176193d7f3")  
  
### <a name="to-host-the-reports-on-report-server"></a>若要承载报表服务器上的报表  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，右键单击解决方案资源管理器中的项目名称，然后单击**属性**。  
  
2. 在报表属性页对话框中，单击**Configuration Manager**，然后选择下的复选框**部署**列。 单击 **“关闭”**。  
  
3. 在报表属性页对话框中，对于**StartItem**属性中，选择报表的名称。  
  
4. 在报表属性页对话框中，对于**TargetServerURL**属性，对于报表服务器中，指定一个 URL，然后单击**确定**。 例如：  
  
   ```  
   http://localhost/reportserver  
   ```  
  
    ![指定的报表服务器 URL](../../adapters-and-accelerators/adapter-sap/media/397ddfd6-f3d2-4327-9bc3-1efa22dc2249.gif "397ddfd6-f3d2-4327-9bc3-1efa22dc2249")  
  
5. 右键单击解决方案资源管理器中的项目名称，然后单击**生成**。  
  
6. 右键单击解决方案资源管理器中的项目名称，然后单击**部署**。  
  
7. 启动 IIS。 单击**启动**，单击**运行**，类型`inetmgr`，然后按`Enter`。  
  
8. 在中**Internet 信息服务 (IIS) 管理器**管理单元中，展开计算机名称，展开**网站**，展开**Default Web Site**，右键单击**ReportServer**，然后单击**浏览**。  
  
9. 在右窗格中，单击该项目的名称，然后单击上的报表的名称。  
  
10. 如果选择了创建数据源时**凭据提示**选项，输入 SAP 系统的用户名和密码，然后单击**查看报告**。  
  
11. 如果指定了查询您创建报表服务器项目需要的参数时，必须输入参数的值。 例如，查询中指定[SAP 数据提供程序用于创建报表服务器项目](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)主题中，需要指定参数，参数的值。  
  
     如果需要，指定参数的值，然后单击**查看报表**。  
  
     ![指定用于生成报表的参数](../../adapters-and-accelerators/adapter-sap/media/221c8c12-4e4f-47f5-9289-9e9212cf6e25.gif "221c8c12-4e4f-47f5-9289-9e9212cf6e25")  
  
    > [!TIP]
    >  你还可以通过为报表提供 URL 查看直接从 web 浏览器。 报表的典型 URL `is http://localhohost/reportserver/<report_name>`。  
  
## <a name="see-also"></a>请参阅  
 [使用包含 SSRS 的 SAP 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)