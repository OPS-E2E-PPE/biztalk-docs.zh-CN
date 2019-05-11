---
title: BPEL 导入 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- examples, orchestrations
- examples, BPEL Import Wizard
- BPEL, examples
- BPEL Import Wizard, examples
- BPEL Import Wizard, orchestrations
ms.assetid: 3fc70608-ccd9-4249-b238-c09fc6551db1
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d86d5b519d05c01389cff1c5a46e071c51e091a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357862"
---
# <a name="bpel-import-biztalk-server-sample"></a>BPEL 导入 （BizTalk Server 示例）
BPEL 导入示例演示如何从业务流程执行语言 (BPEL) 流程说明和及其相关的项目创建业务流程。  

## <a name="what-this-sample-does"></a>本示例的用途  
 Wide World Importers 是一家送货公司向零售商提供自动送货服务。 具体而言，Wide World Importers 使零售商能够：  

- 请求订单发货  

- 跟踪发货  

- 确认发货  

- 确认发货的发票和付款  

  虽然可以通过使用 Web 服务描述语言 (WSDL) 文档表示这些服务的可用性，BPEL 文档描述了产品公司应调用的服务以及如何获得响应从范围中的常见方式世界上导入程序。  

  当 Northwind traders 请 Wide World Importers 负责处理其送货时，它们会提供一份 BPEL 文件和一些相关描述整个交互的项目。 使用 BPEL 文件，Northwind Traders 将创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Wide World Importers 的应用程序 (BPELShipping) 来自动处理订单。  

  此示例将指导你完成此方案，其中 BPELShipping 应用程序：  

1. 从 Northwind Traders 客户订单系统接收订单。  

2. 将发货请求发送到 Wide World Importers 并请求确认。  

3. 从 Wide World Importers 接收发货请求确认。  

4. 从 Wide World Importers 接收提货通知。  

5. 接收到的发货状态消息和包括当客户接收到发货。  

6. 从 Wide World Importers 接收发票。  

7. 发票确认响应 Wide World Importers。  

8. 从 Wide World Importers 接收付款确认。  

9. 将最终发货确认发送到订单系统。  

   单独的 BizTalk 应用程序 (ShipperProcess) 用于为本示例模拟 Wide World Importers。 BPELShipping 应用程序通过使用文件传输协议，从而为通信使用常见的文件系统位置与 ShipperProcess 进行通信。  

## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 为 Web services 的 BPEL 是一种基于 XML 的语言来描述业务流程，以便它可以方便地共享公司想要进行业务往来的使用 Web 服务彼此之间。 BPEL 描述了如何处理业务流程在商业协议级别，但不描述公司，如一家公司将执行从合作伙伴收到后处理采购订单的步骤中的内部过程。 此示例旨在演示如何导入 BPEL 和相应的 WSDL 文件，将它们转换成业务流程，然后开始运行与合作伙伴的业务流程。  

 下面是演示如何导入 BPEL 和 WSDL 文件并将其转换成与预生成的 BizTalk 应用程序 (ShipperProcess) 进行交互的业务流程的分步过程。 如果您完成以下步骤，您不需要执行"生成并初始化 BPELShipping 应用程序"中所述的步骤。  

#### <a name="to-import-from-bpel-and-build-a-working-solution"></a>若要导入 BPEL 并生成工作解决方案  

1. 在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，单击**新建**，然后单击**项目**。  

   > [!NOTE]
   >  执行此过程之前，必须设置 ShipperProcess 应用程序来创建支持的流程和架构项目。  

2. 在中**新的项目**对话框中，在项目类型窗格中，选择**BizTalk （项目）**。 在模板窗格中选择**BizTalk (Server) BPEL 导入项目**。  

3. 在中**名称**框中，输入**BPELShipping**。  

   > [!NOTE]
   >  如果使用不同的名称，可能会遇到问题的最后的绑定步骤。  

4. 选择项目的位置，然后单击**确定**启动 BPEL 导入向导。  

5. 上**欢迎**页上，单击**下一步**。  

6. 上**选择 BPEL、 WSDL 和 XSD 文件**页上，单击**浏览**。  

7. 选择中的所有文件\<*示例路径*\>\Orchestrations\BPELImport\BPELSource 文件夹中，单击**打开**，然后单击**下一步**.  

   > [!NOTE]
   >  在此步骤中，选择要描述业务流程的 BPEL 和 WSDL 文件和 XSD 文件来表示业务文档架构。  

8. 上**为 Invoked WebServices 选择 WSDL 文件**页上，单击**完成**。  

9. BPEL 导入向导报告成功导入后，关闭向导。 现在创建该项目。  

10. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 为项目位置。  

11. 运行下面的命令：  

     **sn – k BPELShipping.snk**  

12. 在解决方案资源管理器中右键单击**BPELShipping**项目，并单击**属性**。  

13. 下**常见属性**，选择程序集密钥文件**BPELShipping.snk**步骤 11 中创建，然后单击**确定**。  

14. 在解决方案资源管理器，选择所有.xsd 文件，并将其删除。  

15. 在解决方案资源管理器中选择**添加引用**，然后在**项目**选项卡上，单击**浏览**。  

16. 选择**ShippingSchemas.dll**从位置\<*示例路径*\>\Orchestrations\BPELImport\Solution\ShipperProcess\ShippingSchemas\bin\Development，和然后单击**确定**。  

    > [!NOTE]
    >  "要生成并初始化 ShipperProcess 应用程序"的部分中说明了如何生成此。  

17. 在解决方案资源管理器中双击**OrderShippingProcess.bpel.odx**。  

18. 上**视图**菜单中，选择**其他 Windows/业务流程视图**。  

19. 在业务流程视图窗口中，右键单击**业务流程属性**，然后单击**属性窗口**。  

20. 在属性窗口中设置**业务流程可导出**属性设置为**False**。  

21. 在解决方案资源管理器中双击**OrderShipping.wsdl.odx**。  

22. 在业务流程视图窗口中，展开**类型/多部分消息类型**。  

23. 展开**InvoiceAckMessageType** ，然后单击**InvoiceAckMessagePart**。  

24. 在属性窗口中，展开**类型**字段，然后选择**从引用的程序集的架构/选择**。  

25. 在中**选择项目类型**对话框中，单击**ShippingSchemas**，选择**Imported_InvoiceAckMessage**键入，然后依次**确定**.  

    > [!NOTE]
    >  在步骤 23 至 25，您将为参与 BPEL 流程 ShippingSchemas 中描述的相应消息类型的服务的消息类型。  

26. 使用以下值每种消息类型重复步骤 23 至 25。  


    |          消息部分          |                    消息类型                     |
    |--------------------------------|-----------------------------------------------------|
    |       InvoiceMessagePart       |       ShippingSchemas.Imported_InvoiceMessage       |
    |      OrderAckMessagePart       |      ShippingSchemas.Imported_OrderAckMessage       |
    |        OrderMessagePart        |        ShippingSchemas.Imported_OrderMessage        |
    | PaymentConfirmationMessagePart | ShippingSchemas.Imported_PaymentConfirmationMessage |
    | PickupNotificationMessagePart  | ShippingSchemas.Imported_PickupNotificationMessage  |
    |  ShipConfirmationMessagePart   |  ShippingSchemas.Imported_ShipConfirmationMessage   |
    |      ShippingHistoryPart       |      ShippingSchemas.Imported_ShippingHistory       |
    |   ShipRequestAckMessagePart    |   ShippingSchemas.Imported_ShipRequestAckMessage    |
    |     ShipRequestMessagePart     |     ShippingSchemas.Imported_ShipRequestMessage     |
    |     ShipStatusMessagePart      |     ShippingSchemas.Imported_ShipStatusMessage      |


27. 在解决方案资源管理器中右键单击**BPELShipping**项目，指向**添加**，然后单击**现有项**。  

28. 从位置选择所有.btm 文件\<*示例路径*\>\Orchestrations\BPELImport\Solution\BPELShipping\BPELShipping。  

29. 在业务流程视图窗口中，找到**消息赋值**形状命名的 MessageAssignment_1 揅 constructmessage1 中，然后将其删除。  

30. 从工具箱拖动**转换**形状揅 constructmessage1 形状。  

31. 在属性窗口中，单击省略号按钮 (**...**)，然后打开**转换配置**对话框。  

32. 选择**现有的映射**。  

33. 选择作为完全限定的映射名称**BPELShipping.Order2ShipRequest**。  

34. 选择作为源**顺序。OrderMessagePart**。  

35. 选择作为目标**ship_request。ShipRequestMessagePart**然后单击**确定**。  

36. 为每个重复步骤 29 至 35**消息赋值**形状并将其替换为**转换**根据下表的形状。  


    |  要替换的形状   |              要使用映射              |      源文档       |       目标文档        |
    |---------------------|--------------------------------------|----------------------------|-----------------------------------|
    | MessageAssignment_2 |     BPELShipping.Order2OrderAck      |   order.OrderMessagePart   |   order_ack.OrderAckMessagePart   |
    | MessageAssignment_3 |     BPELShipping.Order2OrderNAck     |   order.OrderMessagePart   |   order_ack.OrderAckMessagePart   |
    | MessageAssignment_4 |    BPELShipping.Order2ShipHistory    |   order.OrderMessagePart   | ship_history.ShippingHistoryPart  |
    | MessageAssignment_5 |  BPELShipping.ShipHistory2Completed  |   order.OrderMessagePart   | ship_history.ShippingHistoryPart  |
    | MessageAssignment_6 |       BPELShipping.Invoice2Ack       | invoice.InvoiceMessagePart | invoice_ack.InvoiceAckMessagePart |
    | MessageAssignment_7 | BPELShipping.Order2FinalConfirmation |   order.OrderMessagePart   | order_shipped.OrderAckMessagePart |


37. 保存该业务流程。  

38. 双击**Rule_1**中**判定**形状**Decision_1**。  

39. 在 BizTalk 表达式编辑器中，替换  

     ship_request_ack(BPELShipping.Ship_Acknowledged) == true  

     使用  

     ship_request_ack(ShippingSchemas.Ship_Acknowledged) == true  

40. 双击**循环**名为形状**Loop_1**。  

41. 在 BizTalk 表达式编辑器中，替换  

     ship_history(BPELShipping.Ship_Completed) == true  

     使用  

     ship_history(ShippingSchemas.Ship_Completed) == true  

42. 双击**Rule_2**中**判定**形状**Decision_2**。  

43. 在 BizTalk 表达式编辑器中，替换  

     ship_status(BPELShipping.ShipStatus) == "DONE"  

     使用  

     ship_status(ShippingSchemas.ShipStatus) == "DONE"  

44. 在业务流程视图中，展开**类型/相关类型**然后单击***OrderCorrelationSet_Type\\***。  

45. 在属性窗口中，单击省略号按钮 (**...**) 上**相关属性**。  

46. 在上窗格相关联的属性，单击**BPELShipping.OrderID**，然后单击**删除**。  

47. 在可用属性窗格中，展开**发货架构**，选择**订单 ID**，然后单击**添加**。  

48. 单击“确定” 。  

49. 保存所有文件并生成解决方案。  

50. 部署解决方案。  

51. 浏览到的位置\<*示例路径*\>\Orchestrations\BPELImport\Solution\BPELShipping，然后双击**BindAndStartOnly.bat**绑定和启动业务流程。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径\>* \Orchestrations\BPELImport  

 下表显示了本示例中的文件及其用途说明：  

|文件|Description|  
|---------------|-----------------|  
|BPELSource\InvoiceAckMessage.xsd|发票确认架构。|  
|BPELSource\InvoiceMessage.xsd|发票的架构。|  
|BPELSource\OrderAckMessage.xsd|订单确认架构。|  
|BPELSource\OrderHeader.xsd|订单头部架构。|  
|BPELSource\OrderMessage.xsd|订单消息架构。|  
|BPELSource\OrderShipping.wsdl|Bpel 引用的 WSDL 文件。|  
|BPELSource\OrderShippingProcess.bpel|BPEL 处理流程。|  
|BPELSource\PaymentConfirmationMessage.xsd|付款确认消息。|  
|BPELSource\PickupNotificationMessage.xsd|提货通知消息。|  
|BPELSource\ShipConfirmationMessage.xsd|发货确认消息。|  
|BPELSource\ShippingHistory.xsd|发货历史记录文档。|  
|BPELSource\ShipRequestAckMessage.xsd|发货请求确认。|  
|BPELSource\ShipRequestMessage.xsd|发货请求消息。|  
|BPELSource\ShipStatusMessage.xsd|发货状态消息。|  
|Solution\bindings\BPELBindings.xml|指定的端口绑定 BPELShipping 业务流程的绑定文件。|  
|Solution\bindings\ShipperBindings.xml|指定的端口绑定 ShipperProcess 业务流程的绑定文件。|  
|Solution\BPELShipping\BindAndStartOnly.bat|若要使用的绑定和启动后手动生成和部署 BPELImport 业务流程的批处理文件。|  
|Solution\BPELShipping\cleanup.bat|要用于删除 BPELShipping 流程的批处理文件。|  
|Solution\BPELShipping\Setup.bat|要用于安装和启动提供的 BPELShipping 示例的批处理文件。|  
|Solution\BPELShipping\BPELShipping.sln|预生成的 BPELShipping 示例。|  
olution\BPELShipping\BPELShipping\Invoice2Ack.btm|开发票到发票确认的映射。|  
|Solution\BPELShipping\BPELShipping\Order2FinalConfirmation.btm|将订单消息转换为最终发货确认的映射。|  
|Solution\BPELShipping\BPELShipping\Order2OrderAck.btm|将订单消息转换为订单确认的映射。|  
|Solution\BPELShipping\BPELShipping\Order2OrderNack.btm|将订单消息转换为订单否定确认的映射。|  
|Solution\BPELShipping\BPELShipping\Order2ShipHistory.btm|用于将订单消息转换为发货历史记录文档的映射。|  
|Solution\BPELShipping\BPELShipping\Order2ShipRequest.btm|将转换为订单发货请求的订单消息映射。|  
|Solution\BPELShipping\BPELShipping\ShipRequest2Completed.btm|若要设置已完成将发货历史记录的映射。|  
|Solution\ShipperProcess\setup.bat|若要生成、 部署、 绑定和启动 ShipperProcess 助手业务流程和其端口的批处理文件。|  
|Solution\ShipperProcess\cleanup.bat|若要停止、 取消登记和取消部署 ShipperProcess 助手业务流程和其端口的批处理文件。|  

## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 第一步是生成并初始化用于模拟 Wide World Importers 的 ShipperProcess 应用程序。  

#### <a name="to-build-and-initialize-the-shipperprocess-application"></a>若要生成并初始化 ShipperProcess 应用程序  

1. 启动**Visual Studio 命令提示符**。  

2. 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 的以下文件夹：  

    *\<Samples Path\>* \Orchestrations\BPELImport\Solution\ShipperProcess  

3. 运行文件 Setup.bat，以执行以下操作：  

   -   生成 ShippingSchemas 项目，它包含 ShipperProcess 和 BPELShipping 流程使用的架构  

   -   生成 ShipperProcess  

   -   部署 ShippingSchemas 和 ShipperProcess 项目  

   -   创建并绑定发送和接收 ShipperProcess 使用的端口  

   -   启动 shipperprocess 使用的端口  

   -   登记并启动 ShipperProcess 业务流程  

   在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。 可能会显示一个或多个以下的警告;可以忽略这些警告。  

```  
The 'http://contoso.org/samples/Fragments:XXXX' element is not declared. An error occurred at , (35, 16).  
<SAMPLE_LOCATION>\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(667,22): convoy found at 'activate receive(Receive_ShipOrder.Operation_1, Request, initialize Correl)'  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): and 'receive(ReceiveInvoiceAck.Operation_1, Invoice_Ack, Correl)'  
```  

> [!NOTE]
>  不需要执行以下步骤，如果你已完成"以导入 bpel 并生成工作解决方案。"中所述的步骤  

#### <a name="to-build-and-initialize-the-bpelshipping-application"></a>若要生成并初始化 BPELShipping 应用程序  

1. > [!WARNING]
   >  执行这些步骤之前, 必须完成上面标题为"生成并初始化 ShipperProcess 应用程序"步骤。  

    从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 的以下文件夹：  

    *\<Samples Path\>* \Orchestrations\BPELImport\Solution\BPELShipping  

2. 运行文件 Setup.bat，以执行以下操作：  

   -   生成 BPELShipping 项目  

   -   部署 BPELShipping 项目  

   -   创建并绑定发送和接收 BPELShipping 流程使用的端口  

   -   启动 BPELShipping 流程使用的端口  

   -   登记并启动 BPELShipping 业务流程  

## <a name="running-this-sample"></a>运行本示例  

#### <a name="to-run-the-bpel-import-sample"></a>若要运行 BPEL 导入示例  

1.  复制**Order.xml**文件从*\<示例路径\>* \Orchestrations\BPELImport\Solution 文件夹\<*示例路径\>* \Orchestrations\BPELImport\Solution\Ports\ReceiveOrder 文件夹。  

2.  BPELShipping 业务流程提取此文件作为订单从客户订单处理系统中，运行发货流程，并生成一个文件中的每个\<*示例路径*\>\Orchestrations\BPELImport\Solution\Ports\SendOrder 文件夹和\<*示例路径*\>\Orchestrations\BPELImport\Solution\Ports\FinalConfirmation 文件夹。 这些文件的名称的格式是\< *MessageID*\>.xml，其中*\<MessageID\>* 生成的 GUID 来唯一地标识消息。  

## <a name="uninstalling-this-sample"></a>卸载本示例  

#### <a name="to-uninstall-the-bpel-import-sample"></a>卸载 BPEL 导入示例  

1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 对\<*示例路径*\>\Orchestrations\BPELImport\BPELShipping。  

2. 运行 Cleanup.bat。  

3. 浏览到\<*示例路径*\>\Orchestrations\BPELImport\ShipperProcess。  

4. 运行 Cleanup.bat。  

## <a name="see-also"></a>请参阅  
 [业务流程（BizTalk Server 示例文件夹）](../core/orchestrations-biztalk-server-samples-folder.md)