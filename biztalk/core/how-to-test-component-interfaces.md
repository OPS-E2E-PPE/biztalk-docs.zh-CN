---
title: 如何测试组件接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing component interfaces
- component interfaces, testing
ms.assetid: d637f76d-170d-4543-a2b2-a4ac4001386b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8450177cd97d7136d8ee4146ff93fceee20b351
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333859"
---
# <a name="how-to-test-component-interfaces"></a>如何测试组件接口
适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用 PeopleSoft 元数据和组件接口;因此，它可以处理新的或已修改的组件接口。 适配器组件接口中进行任何假设，只不过逻辑并且有效。 因此，每个组件接口必须为适配器作为源使用之前进行测试。  
  
 如果由用户或 peoplesoft 软件升级，对基础应用程序进行更改，并且所做的更改使之无效的组件接口，用户必须首先修复无效的组件接口之前，适配器将使用它。  
  
### <a name="to-test-a-component-interface"></a>若要测试组件接口  
  
1.  在应用程序设计器上**工具**菜单上，单击**测试组件接口**。  
  
     ![](../core/media/psadapter-54-ps-testcompinterface1.gif "PSAdapter_54_PS_TestCompInterface1")  
  
2.  在中**Component Interface Tester**对话框框中，通过使用以下方法之一测试组件接口。 完成更改后，右键单击窗格顶部的项目。  
  
    > [!NOTE]
    >  如果需要，单击对话框中，将其置于前台。  
  
    -   若要测试组件接口使用 Find 方法，请单击**查找**。  
  
         **Component Interface Tester-查找结果**对话框将打开，显示针对该底层组件的所有可能的项。 如果有 300 多个项，会显示一条消息。  
  
         a. 在左窗格中**查找结果**对话框中，选择一个字段。  
  
         b. 若要显示该特定字段的相关数据，请单击**获取的所选**。  
  
         出现以下屏幕。  
  
         ![](../core/media/psadapter-55-ps-testcompinterface2.gif "PSAdapter_55_PS_TestCompInterface2")  
  
         如果安全设置允许，可以更改中的每个字段的值。  
  
         此时将打开以下对话框。  
  
         ![](../core/media/psadapter-56-ps-testcompinterface3.gif "PSAdapter_56_PS_TestCompInterface3")  
  
    -   若要测试组件接口使用`Get`方法：  
  
         a. 输入现有键。  
  
         b. 单击**获取现有**。  
  
         这会返回您输入的密钥的公开的属性。  
  
         您可以更改值，如果**更新访问**指定。  
  
         或者，您可以使用测试`Create`方法。  
  
         ![](../core/media/psadapter-57-ps-testcompinterface4.gif "PSAdapter_57_PS_TestCompInterface4")  
  
    -   若要测试组件接口使用`Create`方法：  
  
         a. 输入所有所需的密钥值。  
  
         b. 单击**创建新的**。  
  
         当输入中的有效值**创建密钥**，完成对默认数据扩展表名称后，将打开显示 JOBCODE 数据的窗格。  
  
         可以现在更改字段。  
  
         ![](../core/media/psadapter-58-ps-testcompinterface5.gif "PSAdapter_58_PS_TestCompInterface5")  
  
         更改针对组件的基础业务逻辑对进行验证。  
  
3.  若要保存所做的更改，请单击**保存**图标。  
  
     用于创建记录的密钥可以用于查看数据的 Get 方法。 可以在 PeopleSoft Component 中查看已添加的数据，如下面的示例中所示。  
  
     ![](../core/media/psadapter-59-ps-testcompinterface6.gif "PSAdapter_59_PS_TestCompInterface6")  
  
     **生效日期**是默认值之一。  
  
## <a name="see-also"></a>请参阅  
 [附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)   
 [附录 c:使用组件接口](../core/appendix-c-using-component-interfaces.md)