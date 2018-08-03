---
title: 步骤 7： 创建和配置端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
- private process tutorial, configuring ports
ms.assetid: c00344c6-506a-4560-a948-e5fed2b9fd58
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44a9696f907928f31a740e4d8545567921a82df9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965235"
---
# <a name="step-7-creating-and-configuring-ports"></a>步骤 7： 创建和配置端口
在此步骤中，您将创建和配置用于与业务流程进行通信的端口。 每个端口都具有类型、方向和绑定属性。 这些属性确定通信的方向和模式、发送或接收消息的位置以及通信方式。  
  
### <a name="to-create-a-logical-send-port"></a>创建逻辑发送端口  
  
1.  在 Visual Studio 中，从工具箱拖动**端口**形状变为业务流程设计图面并将其放在**端口图面**以打开**端口配置向导**。  
  
2.  上**端口配置向导**页上，单击**下一步**。  
  
3.  上**端口属性**页上，在**名称**框中，键入**ContosoSQLReqResponsePort**，然后单击**下一步**。  
  
4.  上**选择端口类型**页上，在**端口类型名称**框中，键入**ContosoSQLReqResponsePortName**。  
  
5.  有关**通信模式**，选择**请求-响应**。  
  
6.  有关**访问限制**，选择**内部使用-局限于此项目**，然后单击**下一步**。  
  
7.  上**端口绑定**页上，选择**我将发送请求并接收响应**，保留**端口绑定**选项设置为**指定更高版本**，然后单击**下一步**。  
  
8.  单击**完成**以创建该端口。  
  
### <a name="to-change-the-variable-type-for-the-orchestration-ports"></a>更改业务流程端口的变量类型  
  
1.  在业务流程视图中，展开**类型**，展开**端口类型**，展开**ContosoSQLReqResponsePortName**，展开**Operation_1**，然后选择**请求**。  
  
2.  在属性窗口中，选择**消息类型**属性中，展开**架构**，然后单击**\<从引用的程序集选择\>**.  
  
3.  在选择项目类型对话框中，单击**ContosoPriceAndAvailability**。  
  
4.  在右窗格中，选择**rootPriceRequest**，然后单击**确定**。  
  
5.  在业务流程视图中，在**Operation_1**，选择**响应**为**ContosoSQLReqResponsePortName**端口类型。  
  
6.  在属性窗口中，选择**消息类型**属性中，展开**架构**，然后单击\<**从引用的程序集选择\>**.  
  
7.  在**选择项目类型**对话框中，单击**ContosoPriceAndAvailability**。  
  
8.  在右窗格中，选择**rootPriceResponse**，然后单击**确定**。  
  
### <a name="to-connect-the-ports-to-the-receive-shapes"></a>将端口连接到“接收”形状  
  
1.  在业务流程设计图面上，选择**Send_1**形状。  
  
2.  在属性窗口中，选择**消息**属性，，然后选择**Contoso3A2RequestMessage**从下拉列表。  
  
3.  连接**ContosoSQLReqResponsePort**通过旁边选择绿色句柄**请求**标签和将其拖到绿色句柄**Send_1**形状。  
  
4.  在业务流程设计图面上，选择**Receive_1**形状。  
  
5.  在属性窗口中，选择**消息**属性，，然后选择**Contoso3A2ResponseMessage**从下拉列表。  
  
6.  连接**ContosoSQLReqResponsePort**通过旁边选择绿色句柄**响应**标签和将其拖到绿色句柄**Receive_1**形状。  
  
7.  在**文件**菜单上，单击**保存所有**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 8：生成和部署 Contoso 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/step-8-building-and-deploying-the-contoso-orchestration.md)