---
title: 步骤 3：创建应用程序定义文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 843fafdb-571e-4da4-ad04-7dc7f23e03ac
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 455a4423a1fe420ec9a46fe8cb8236086e3f4309
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363252"
---
# <a name="step-3-create-an-application-definition-file"></a>步骤 3：创建应用程序定义文件
![步骤 3，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **若要完成的时间：** 15 分钟  
  
 Microsoft Office SharePoint Server 中的业务数据目录功能公开，并将业务线 (LOB) 应用程序中的数据合并到门户。 若要将此数据合并到您的门户网站，必须生成可以使用 Microsoft Office SharePoint Server 应用程序定义文件。  
  
 在此步骤中使用 Business Data Catalog Definition Editor 工具，适用于 Microsoft Office SharePoint Server 2007 SDK，为业务数据目录中创建应用程序定义文件。 此定义文件描述 Echo 适配器的 EchoGreetings 方法，并将在后续步骤中用于启用 SharePoint 与适配器进行通信。  
  
 要创建的 Microsoft Office SharePoint Server 应用程序的用途是允许您调用 Echo 适配器的 EchoGreetings 方法并使用 SharePoint Web 部件将响应返回。  
  
## <a name="prerequisites"></a>先决条件  
 您应当已完成[步骤 2:将 Web 项目部署](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)。 您还必须访问到 Business Data Catalog Definition Editor，作为 Microsoft Office SharePoint Server 2007 SDK 的一部分安装。 你可以下载从 SDK [ http://go.microsoft.com/fwlink/?LinkId=104130 ](http://go.microsoft.com/fwlink/?LinkId=104130)。  
  
## <a name="creating-an-application-definition-file"></a>创建应用程序定义文件  
 本主题提供创建在 IIS 中承载的 WCF 适配器与连接的 SharePoint 业务数据目录应用程序定义文件的分步说明。  
  
#### <a name="to-connect-to-the-wcf-adapter-service-and-create-entities"></a>若要连接到 WCF 适配器服务并创建实体  
  
1.  从**开始菜单**，依次指向**所有程序**，然后单击**Microsoft Business Data Catalog Definition Editor**。  
  
2.  在工具栏上，单击**添加 LOB 系统**。  
  
3.  在添加 LOB 系统窗口中，单击**连接到 web 服务**。  
  
4.  在中**URL**框中，键入 WCF 服务的 URL。 该 URL 必须采用以下格式： `https://machinename/EchoWeb/EchoOutboundContract.svc?wsdl`  
  
5.  单击 **“连接”**。  
  
6.  若要查看可用的操作，请单击**添加 Web 方法**选项卡。您应看到 EchoGreetings 方法。 将方法拖至设计图面。  
  
7.  单击“确定” 。  
  
8.  在中**输入 LOB 系统的名称**对话框中键入名称**LOB 系统名称**框。 对于此示例中，输入**EchoWSLOB**，然后单击**确定**。  
  
9. 展开**EchoWSLob**节点，然后展开**实体**节点。 选择**Entity0**并在属性窗格中键入**EchoGreetings**的值作为**名称**属性。  
  
     ![实体名称](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/942e7853-451e-4cf5-8884-09fb7d8dc19d.gif "942e7853-451e-4cf5-8884-09fb7d8dc19d")  
  
## <a name="specify-user-name-and-password-headers-for-the-method"></a>该方法为指定的用户名和密码标头  
 在调用 WCF 适配器时，可能需要提供用户凭据将传递到 LOB 系统。 在[步骤 1:使用适配器服务开发向导创建 Web 项目](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)，配置 Echo 适配器需要的 MyUserHeader 和 MyPassHeader 字段中提供的用户名和密码信息。 现在必须使用此应用程序定义文件的相同字段名称。  
  
#### <a name="to-specify-user-name-and-password-headers"></a>若要指定用户名称和密码标头  
  
1.  在元数据对象窗格中，展开**EchoGreetings**节点，然后展开**方法**节点。  
  
2.  单击**EchoGreetings**节点，然后在属性窗格中，单击旁边的省略号 **（...）** 按钮**属性**字段。  
  
3.  在 PropertyView 集合编辑器窗口中，单击**添加**，然后在**名称**字段的属性窗格中，键入**HttpHeaderUserName**。  
  
     ![指定用户名标题字段](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8da4d1b7-0792-407a-ba93-ba749138dd14.gif "8da4d1b7-0792-407a-ba93-ba749138dd14")  
  
4.  在中**PropertyValue**字段中，键入**MyUserHeader**。  
  
5.  单击**外**，然后在属性窗格中键入**HttpHeaderPassword**对于名称字段中，然后键入**MyPassHeader**为**PropertyValue**字段。  
  
6.  单击“确定” 。  
  
## <a name="set-up-single-sign-on-for-connecting-to-the-echo-adapter"></a>设置了单一登录连接到 Echo 适配器  
 SharePoint 使用从单一登录信息的 MyUserHeader 和 MyPassHeader 使用身份验证的值填充。 若要链接到单一登录此应用程序定义文件，必须提供 SecondarySsoApplicationId。  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a>若要设置 SecondarySsoApplicationId 属性  
  
1. 在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**实例**节点。  
  
2. 单击**EchoWSLOB_Instance**，然后在属性窗格中，单击省略号<strong>（...）</strong>按钮**属性**字段。  
  
3. 在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**SecondarySsoApplicationId**中**名称**字段。  
  
4. 在中**PropertyValue**字段中，键入**EchoSSO**。  
  
    ![设置 SecondarySsoApplicationId](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/68e6be61-77af-46b1-8ff0-b8538c526228.gif "68e6be61-77af-46b1-8ff0-b8538c526228")  
  
5. 单击“确定” 。  
  
## <a name="create-input-filters-and-default-values"></a>创建输入筛选器和默认值  
 应用程序定义文件必须能够接受用户输入可以传递给 Web 服务。 若要实现此目的，必须执行以下一组任务：  
  
#### <a name="to-create-a-filter-and-map-it-to-the-greeting-parameter"></a>若要创建筛选器，并将其映射到问候语参数  
  
1.  在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**方法**节点。  
  
2.  展开**EchoGreetings**方法中，右键单击**筛选器**，然后单击**添加筛选器**。  
  
3.  在属性窗格中，键入**问候**中**名称**字段。  
  
     ![设置筛选器名称](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/74036b9e-7eec-4156-b238-840e67a2f00c.gif "74036b9e-7eec-4156-b238-840e67a2f00c")  
  
4.  在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**方法**节点  
  
5.  展开**EchoGreetings**方法，然后展开**参数**节点。  
  
6.  展开**问候**节点，然后展开第二个**问候**节点。  
  
7.  单击**greetingText**节点，然后在属性窗格中，选择**问候**从**FilterDescriptor**列表。  
  
#### <a name="to-create-a-finder-method-instance-for-the-echogreetings-method"></a>若要创建 Finder 方法实例 EchoGreetings 方法  
  
1.  在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**方法**节点。  
  
2.  展开**EchoGreetings**方法中，右键单击**实例**，然后单击**添加方法实例**以打开创建方法实例窗口。  
  
3.  在创建方法实例窗口中，单击**Finder**有关**方法实例类型**，然后选择**返回**为**返回 TypeDescriptor**.  
  
     ![创建方法实例](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a932a7a0-c004-46bf-af5c-cc7392bafa43.gif "a932a7a0-c004-46bf-af5c-cc7392bafa43")  
  
4.  单击“确定” 。  
  
5.  在属性窗格中，键入**EchoGreetings_Instance**中**名称**字段。  
  
#### <a name="to-set-default-parameters"></a>若要设置默认参数  
  
1.  在元数据对象窗格中，展开**EchoWSLOB**节点，然后展开**方法**节点。  
  
2.  展开**EchoGreetings**方法，然后展开**实例**节点。  
  
3.  选择**EchoGreetings_Instance**方法实例，并在属性窗格中，单击省略号按钮 （...） 在**DefaultValues**字段。  
  
4.  在编辑窗口中，展开**问候**节点，然后展开第二个**问候**节点。 展开**名称**节点，直到完全显示树状结构。  
  
5.  在编辑窗口中，设置字段值，如下所示：  
  
    |将此项设置|与此|  
    |--------------|-------------|  
    |**id**|GUID 值，例如 27829ed4 583a-40 c 4 ad87 fb8cdd9dc98d。|  
    |**sentDateTime**|当前日期和时间，例如 05/15/08 上午 9:12 点|  
    |**firstName**|第一个|  
    |**middleName**|中间|  
    |**lastName**|上一次|  
  
     ![默认参数](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/70250957-9680-48ce-8bce-420ff18bb47a.gif "70250957-9680-48ce-8bce-420ff18bb47a")  
  
6.  单击 **“关闭”**。  
  
### <a name="to-export-the-application-definition-file"></a>若要导出的应用程序定义文件  
  
1.  在元数据对象窗格中，右键单击**EchoWSLOB**节点，并单击**导出**。  
  
2.  将文件另存 EchoWS.xml。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 Business Data Catalog Definition Editor 工具具有用于创建可以导入到 Microsoft Office SharePoint Server 2007，以便与您在 IIS 中承载的适配器的连接应用程序定义文件。  
  
## <a name="next-steps"></a>后续步骤  
 现在，您必须创建 SharePoint 应用程序根据在此步骤中创建的应用程序定义文件。 请参阅[步骤 4:创建 Sharepoint 应用程序以访问适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md)有关的说明。  
  
## <a name="see-also"></a>请参阅  
 [教程 3：在 IIS 中托管 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)