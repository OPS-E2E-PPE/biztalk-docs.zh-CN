---
title: 将 PeopleSoft 架构导入 Visual Studio |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 411f25f4-4431-44e4-84cf-5c515b3e32db
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89534c67d772f8b025289d61ab515f1585791d68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382483"
---
# <a name="import-peoplesoft-schemas-into-biztalk-server-projects"></a>PeopleSoft 架构导入到 BizTalk Server 项目
创建 PeopleSoft Enterprise 系统后，可以浏览服务器和架构导入到 BizTalk Server 项目。  
  
## <a name="browse-a-peoplesoft-server-system"></a>浏览 PeopleSoft 服务器系统  
  
1.  右键单击 BizTalk Server 项目，然后选择以下选项之一。  
  
    -   如果你已为对象生成的架构，请选择**外**，单击**添加架构**，然后选择要向业务流程添加的现有架构。  
  
    -   如果不为对象生成的架构，请选择**外**，然后单击**添加生成的项**，然后选择适配器。 这是相同的名称中输入**AdapterProperties**对话框。 有关详细信息，请参阅 BizTalk 主帮助中的"适配器属性对话框"。  
  
2.  单击“下一步”。  
  
     PeopleSoft Enterprise 系统将显示在浏览器中。  
  
     ![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")  
  
### <a name="component-interfaces"></a>组件接口  
 在中**组件接口**(CI) 文件夹中，您可以在系统中查看所有可用组件接口。 组件接口声明方法和它支持的属性的集。 组件接口不实现行为或属性。 用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器公开了标准方法，例如，CreateEx、 DeleteOnly、 Find、 Get、 和 UpdateEx。 有关这些方法的说明，请参阅[附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)。  
  
## <a name="generate-schemas"></a>生成架构  
  
选择你想要将架构导入的项：**消息**，**查询**，或**组件接口**。  BizTalk Server 生成的选定项的架构，并将其导入 BizTalk Server 项目。  
  
> [!NOTE]
>  如果服务器对象定义发生更改，必须重新生成架构以更新其包含的数据。  
  
## <a name="see-also"></a>请参阅  
 [创建 PeopleSoft 发送处理程序](../core/creating-peoplesoft-send-handlers.md)