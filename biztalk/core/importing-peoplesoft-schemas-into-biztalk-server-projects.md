---
title: "将 PeopleSoft 架构导入到 BizTalk Server 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas, generating
- schemas, importing into BizTalk Server projects
- component interfaces
- BizTalk Server, schemas [PeopleSoft]
- importing schemas into BizTalk Server
ms.assetid: 411f25f4-4431-44e4-84cf-5c515b3e32db
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4946b438adc0d1e4d360b35207ff69e85b4e2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-peoplesoft-schemas-into-biztalk-server-projects"></a>将 PeopleSoft 架构导入到 BizTalk Server 项目中 
在创建 PeopleSoft Enterprise 系统之后，可以浏览服务器并将架构导入 BizTalk Server 项目。  
  
## <a name="browsing-a-peoplesoft-server-system"></a>浏览 PeopleSoft 服务器系统  
 使用适配器向导浏览 PeopleSoft 服务器。  
  
#### <a name="to-browse-a-peoplesoft-server-system"></a>若要浏览 PeopleSoft 服务器系统  
  
1.  右键单击 BizTalk Server 项目，然后选择以下选项之一。  
  
    -   如果已经为你的对象生成的架构，选择**添加**，单击**添加架构，** ，然后选择现有的架构将添加到您的业务流程。  
  
    -   如果你没有为你的对象生成的架构，则选择**添加**，然后单击**添加生成的项**，适配器，然后选择。 这是中输入的相同名称**AdapterProperties**对话框。 有关详细信息，请参阅 BizTalk 主帮助中的“适配器属性对话框”。  
  
2.  单击“下一步”。  
  
     此时 PeopleSoft Enterprise 系统将显示在浏览器中。  
  
     ![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")  
  
### <a name="component-interfaces"></a>组件接口  
 在**组件接口**(CI) 文件夹中，你可以在系统中查看所有可用组件接口。 组件接口声明它所支持的方法和属性集。 组件接口不实现行为或属性。 用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器公开了标准方法，例如 CreateEx、DeleteOnly、Find、Get 和 UpdateEx。 有关这些方法的说明，请参阅[附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)。  
  
## <a name="generating-schemas"></a>生成架构  
 请按照以下步骤生成架构。  
  
#### <a name="to-generate-the-schemas"></a>若要生成架构  
  
-   选择你想要导入架构的项目：**消息**，**查询**，或**组件接口**。  
  
     BizTalk Server 为选定项目生成架构，然后将其导入 BizTalk Server 项目。  
  
    > [!NOTE]
    >  如果服务器对象定义更改，您必须重新生成架构以更新它包含的数据。  
  
## <a name="see-also"></a>另请参阅  
 [创建 PeopleSoft 发送处理程序](../core/creating-peoplesoft-send-handlers.md)