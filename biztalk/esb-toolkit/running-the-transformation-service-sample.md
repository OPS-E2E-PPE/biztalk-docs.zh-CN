---
title: 运行转换服务示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42064d32-5ec5-4219-a338-c5769969b958
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6278287e93211356c5c7440020032c798bc7d16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394035"
---
# <a name="running-the-transformation-service-sample"></a>运行转换服务示例
您可以执行转换服务示例使用任何工具或实用程序，可以执行 Web 服务方法。 例如，可以使用 Storm，可从[CodePlex](http://go.microsoft.com/fwlink/?LinkId=187762) ([http://go.microsoft.com/fwlink/?LinkId=187762](http://go.microsoft.com/fwlink/?LinkId=187762))，也可以创建自己的测试客户端调用转换 Web 服务。  
  
 若要使用.NET Web 服务 Studio 正确安装转换服务示例的测试，到基于 ASMX 的转换 Web 服务输入的 URL **WSDL 终结点**文本框中，，然后单击**获取**按钮。 这将生成可用于调用 ESB 转换 Web 服务，如图 1 中所示的客户端前端接口。  
  
 ![转换服务](../esb-toolkit/media/ch6-transformationservice.gif "Ch6-TransformationService")  
  
 **图 1**  
  
 **使用.NET Web 服务 Studio 测试转换服务示例**  
  
 转换服务示例包含两个 Microsoft BizTalk 映射和两个测试消息的 XML 文档。 使用名为 TEST_CanonicalOrder_to_OrderConfirmation.xml 和 TEST_RetailOrder_to_CanonicalOrder.xml （位于 \Source\Samples\TransformServices\Test\Data 文件夹中） 的 XML 消息，来执行转换 Web 服务。  
  
 该服务将自动转换消息使用的架构 CanonicalOrder.xsd 和 RetailOrder.xsd 和 OrderConfirmation.xsd （位于 \Source\Samples\TransformServices\Source\ESB。TransformServices.Schemas 文件夹中），和.NET Web 服务 Studio 将显示在结果的已转换的消息。 以下过程说明如何测试 CanonicalOrder_To_OrderConfirmation 映射。  
  
 **若要测试 GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_OrderConfirmation 映射**  
  
1.  如果未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。  
  
2.  值作为输入 TEST_CanonicalOrder_to_OrderConfirmation.xml 文件的以下字符串表示形式**消息**中的参数**输入**树视图的.NET Web 服务 Studio。 此字符串符合 GlobalBank.ESB.TransformServices.Schemas.CanonicalOrder 架构：  
  
    ```  
    <ns0:CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1"   
        Status="Status_2" xmlns:ns0=  
        "http://schemas.globalbank.esb.transformservices.com">  
        <OrderHeader><CustomerName>CustomerName_0</CustomerName>  
        <CustomerID>CustomerID_0</CustomerID><ShipToLine1>  
        ShipToLine1_0</ShipToLine1><ShipToLine2>ShipToLine2_0  
        </ShipToLine2><BillToLine1>BillToLine1_0</BillToLine1>  
        <BillToLine2>BillToLine2_0</BillToLine2><OrderTotal>OrderTotal_0  
        </OrderTotal></OrderHeader><OrderDetails><LineItem Qty="Qty_0"   
        PartNum="PartNum_1" Description="Description_2"   
        UnitPrice="UnitPrice_3" Ext="Ext_4" /></OrderDetails>  
        <B2BPartnerDetails CreditLimit="CreditLimit_0"   
        AccountBalance="AccountBalance_1"   
        LastOrderedData="LastOrderedData_2"   
        DiscountLevel="DiscountLevel_3" /></ns0:CanonicalOrder>  
    ```  
  
3.  输入以下字符串的值作为**mapName**中的参数**输入**树视图的.NET Web 服务 Studio。 这是对消息执行的 BizTalk 映射的完整键入的名称：  
  
    ```  
    GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_  
        OrderConfirmation, GlobalBank.ESB.TransformServices.Maps,   
        Version=1.0.0.0, Culture=neutral, PublicKeyToken=<insertYourPublicKeyTokenHere>  
    ```  
  
4.  单击**Invoke**按钮以执行 Web 服务。 **输出**测试框显示结果。