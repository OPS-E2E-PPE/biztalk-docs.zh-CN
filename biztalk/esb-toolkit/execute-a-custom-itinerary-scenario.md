---
title: 执行自定义的路线方案 |Microsoft 文档
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
ms.openlocfilehash: 8659c5b37cba0520fb4a4c0f4c63c8d6ecff37be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294061"
---
# <a name="execute-a-custom-itinerary-scenario"></a>执行自定义的路线方案
你可以使用路线测试客户端应用程序执行路线的自定义方案。  
  
### <a name="to-execute-a-custom-itinerary-scenario-using-the-itinerary-test-client-application"></a>若要执行使用路线测试客户端应用程序的自定义路线方案  
  
1.  在 Windows 资源管理器，打开文件夹 \Source\Samples\Itinerary\Source\ESB。你的安装位置的 Itinerary.Test\bin\Debug[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例并启动名为 Esb.Itinerary.Test.exe 应用程序。  
  
2.  选择中的服务类型**ServiceType**下拉列表中，为请求中，指定一个名称，然后选择**IsRequestResponse**复选框，如果这是请求/响应操作。 可以指定双向操作，并选择要使用 WCF 新版路线 Web 服务;若要执行此操作，请选择中的复选框**Web 服务选项**应用程序窗口顶部的部分。  
  
3.  若要指定冲突解决程序用于中的所选服务**AddResolversfortheService**窗口部分，选择冲突解决程序从下拉列表中，键入，然后单击**AddResolver**。 如果需要，可以添加多个冲突解决程序。 添加所有必需的冲突解决程序后，单击**AddService**按钮以将此服务调用添加到路线。  
  
4.  如果你想要将多个服务调用添加到路线，重复步骤 2 和 3。 你还可以使用**RemoveService**和**ClearServices**按钮可以修改路线中的服务的列表。  
  
5.  如果你想要在其他时间重复当前路线，将完成当前路线存盘通过单击**SaveItinerary**按钮。 通过单击，可以再次加载它**LoadItinerary**按钮。 这意味着你无需在路线中指定的服务和冲突解决程序，每次执行这种情况下使用不同的消息或路线 Web 服务设置。  
  
6.  加载合适的消息。 若要执行此操作，请键入路径和名称中的消息**LoadMessage**文本框中或单击省略号按钮 （…），然后选择必需的消息文件。  
  
7.  单击**SubmitRequest**按钮以提交消息以使用你指定的路线设置的处理。 如果处理返回的结果，这将出现在**结果**文本框。