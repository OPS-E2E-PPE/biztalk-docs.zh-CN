---
title: 执行自定义路线方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fd69e29-e853-4b16-9966-29ab98dd5bea
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1533d2fcea864c1b2effb8afc2dda35c0b36c7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261935"
---
# <a name="execute-a-custom-itinerary-scenario"></a>执行自定义路线方案
可以使用路线测试客户端应用程序来执行自定义路线方案。  

### <a name="to-execute-a-custom-itinerary-scenario-using-the-itinerary-test-client-application"></a>若要执行使用路线测试客户端应用程序的自定义路线方案  

1. 在 Windows 资源管理器中打开文件夹 \Source\Samples\Itinerary\Source\ESB。安装位置的 Itinerary.Test\bin\Debug[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例和启动应用程序名为 Esb.Itinerary.Test.exe。  

2. 选择中的服务类型**ServiceType**下拉列表中，为请求中，指定一个名称，然后选择**IsRequestResponse**复选框，如果这是请求/响应操作。 可以指定双向操作，然后选择要使用路线 Web 服务; 的 WCF 版本若要执行此操作，请选择中的复选框**Web 服务选项**位于应用程序窗口的顶部部分。  

3. 若要指定冲突解决程序以使用与中的所选服务**AddResolversfortheService**部分中的窗口中，选择冲突解决程序从下拉列表中，键入，然后单击**AddResolver**。 如果需要，可以添加多个冲突解决程序。 添加所有必需的冲突解决程序后，单击**AddService**按钮以将此服务调用添加到路线。  

4. 如果你想要将多个服务调用添加到路线，重复步骤 2 和 3。 此外可以使用**RemoveService**并**ClearServices**按钮可以修改的路线中的服务列表。  

5. 如果你想要另找时间重复当前路线，将保存完成当前的旅行计划到磁盘通过单击**SaveItinerary**按钮。 通过单击，可以再次加载它**LoadItinerary**按钮。 这意味着，不需要在路线中指定的服务和冲突解决程序，每次执行此方案中使用不同的消息或旅行计划的 Web 服务设置。  

6. 加载适当的消息。 若要执行此操作，或者键入路径和名称中的消息**LoadMessage**文本框或单击省略号按钮 （...），并选择所需的消息文件。  

7. 单击**SubmitRequest**按钮以提交对具有指定的路线设置进行处理的消息。 如果在处理返回的结果，这将显示在**结果**文本框。
