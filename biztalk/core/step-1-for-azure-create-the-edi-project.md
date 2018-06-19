---
title: （适用于 Azure) 中的步骤 1： 创建 EDI 项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d353129-04f0-456b-b371-b346959f5155
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51264a79480031bd334dfb7d699a3a701f2c0254
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009998"
---
# <a name="step-1-for-azure-create-the-edi-project"></a>（适用于 Azure) 中的步骤 1： 创建 EDI 项目
在本部分中，Contoso 将使用 [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] 2012 年 4 月版本创建一个 EDI 项目。 在此项目中，Contoso 将添加以下内容：  
  
-   内部的销售订单架构 (**ECommerceSalesOrder.xsd**) 到 X12 840 EDI 销售订单架构会进行转换。 在消息被接收到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中之后，Contoso 将使用内部架构处理消息  
  
-   转换 (**EDI840TOSALESORDER。TRFM**) 将 X12 840 销售订单架构**ECommerceSalesOrder**架构。  
  
 在 [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] 的 Azure BizTalk 门户中创建协议时，Contoso 会使用这些项目。  
  
### <a name="to-create-edi-project"></a>创建 EDI 项目  
  
1.  打开 Visual Studio 中，从**文件**菜单中的指向**新建**，然后单击**项目**。  
  
2.  在**新项目**对话框中，从**已安装的模板**，选择**Service Bus**。 指定项目名称以及该项目的位置，然后单击**确定**。  
  
##  <a name="BKMK_CreateSchema"></a>若要创建在 EDI 项目架构  
  
1.  从解决方案资源管理器，右键单击你刚刚创建的项目名称，指向**添加**，然后单击**新项**。  
  
2.  在**添加新项**对话框中，从**已安装的模板**，选择**架构**，指定的名称作为架构**ECommerceSalesOrder.xsd**，然后单击**添加**。  
  
3.  编辑并生成类似如下的架构：  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <xs:schema xmlns="http://ECommerceSalesOrder.Inbound" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://ECommerceSalesOrder.Inbound" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
      <xs:element name="SalesOrder">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="CompanyCode" type="xs:string" />  
            <xs:element name="PartID" type="xs:int" />  
            <xs:element name="Quantity" type="xs:int" />  
            <xs:element name="AskPrice" type="xs:decimal" />  
            <xs:element name="RequestShipmentDate" type="xs:date" />  
            <xs:element name="Address">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Line1" type="xs:string" />  
                  <xs:element name="Line2" type="xs:string" />  
                  <xs:element name="City" type="xs:string" />  
                  <xs:element name="State" type="xs:string" />  
                  <xs:element name="Country" type="xs:string" />  
                  <xs:element name="Zipcode" type="xs:int" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Contact">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Firstname" type="xs:string" />  
                  <xs:element name="Lastname" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Comments" type="xs:string" />  
            <xs:element name="DateNow" type="xs:date" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
     可以使用架构编辑器生成此架构。 有关详细信息，请参阅[使用 BizTalk 编辑器](../core/using-biztalk-editor.md)。  
  
4.  保存该架构。  
  
##  <a name="BKMK_CreateTrfm"></a>若要创建 EDI 项目中转换  
  
1.  从解决方案资源管理器，右键单击你刚刚创建的项目名称，指向**添加**，然后单击**新项**。  
  
2.  在**添加新项**对话框中，从**已安装的模板**，选择**映射**，指定的名称作为架构**Edi840ToSalesOrder.trfm**，然后单击**添加**。  
  
3.  在映射中，对于源架构选择**X12_00401_840.xsd**。 这是用于 EDI 销售订单的标准 X12 架构。 必须已将此架构添加到创建的 EDI 项目中。 你可以下载此示例和其他 X12 架构从[http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)。 X12 架构属于**MicrosoftEdiXSDTemplates.zip**从下载位置可用的包。  
  
4.  对于目标架构中，选择**ECommerceSalesOrder.xsd**。 你在本主题前面的内容中已创建此架构。  
  
5.  通过连接源和目标架构中的相关节点来创建映射。  
  
6.  保存映射。  
  
## <a name="see-also"></a>另请参阅  
 [教程 4： 创建使用 BizTalk Server 2013 的混合应用程序](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)