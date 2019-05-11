---
title: 步骤 1 （适用于 Azure):创建 EDI 项目 |Microsoft Docs
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
ms.openlocfilehash: d0428ae4c288234607c0de3372b8515de162339d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392883"
---
# <a name="step-1-for-azure-create-the-edi-project"></a>步骤 1 （适用于 Azure):创建 EDI 项目
在本部分中，Contoso 创建 EDI 项目使用[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]2012 年 4 月发布。 作为项目的一部分，Contoso 将添加以下：  
  
- 内部销售订单架构 (**ECommerceSalesOrder.xsd**) 到 X12 840 EDI 销售订单架构将被转换。 Contoso 使用内部架构来处理该消息后接收到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- 转换 (**EDI840TOSALESORDER。TRFM**) 将 X12 840 销售订单架构**ECommerceSalesOrder**架构。  
  
  Contoso Azure BizTalk 门户中创建协议时使用这些项目[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]。  
  
### <a name="to-create-edi-project"></a>若要创建 EDI 项目  
  
1.  打开 Visual Studio 中，从**文件**菜单中的指向**新建**，然后单击**项目**。  
  
2.  在中**新的项目**对话框中，从**已安装的模板**，选择**Service Bus**。 指定项目名称和项目的位置，然后单击**确定**。  
  
##  <a name="BKMK_CreateSchema"></a> 若要创建 EDI 项目中架构  
  
1.  从解决方案资源管理器，右键单击刚创建的项目名称，指向**外**，然后单击**新项**。  
  
2.  在中**添加新项**对话框中，从**已安装的模板**，选择**架构**，指定作为架构名称**ECommerceSalesOrder.xsd**，然后单击**添加**。  
  
3.  编辑和生成的架构如下所示：  
  
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
  
     可以使用架构编辑器来生成此架构。 有关详细信息，请参阅[使用 BizTalk 编辑器](../core/using-biztalk-editor.md)。  
  
4.  保存该架构。  
  
##  <a name="BKMK_CreateTrfm"></a> 若要创建 EDI 项目中的转换  
  
1.  从解决方案资源管理器，右键单击刚创建的项目名称，指向**外**，然后单击**新项**。  
  
2.  在中**添加新项**对话框中，从**已安装的模板**，选择**映射**，指定作为架构名称**Edi840ToSalesOrder.trfm**，然后单击**添加**。  
  
3.  在映射中，对于源架构选择**X12_00401_840.xsd**。 这是标准 X12 EDI 销售订单的架构。 您必须具有已将此架构添加到你创建的 EDI 项目。 您可以下载和其他 X12 中的架构[ http://go.microsoft.com/fwlink/p/?LinkId=235057 ](http://go.microsoft.com/fwlink/p/?LinkId=235057)。 X12 架构属于**MicrosoftEdiXSDTemplates.zip**从下载位置提供的包。  
  
4.  对于目标架构中，选择**ECommerceSalesOrder.xsd**。 本主题前面的创建此架构。  
  
5.  通过连接源和目标架构中的相关节点来创建映射。  
  
6.  保存该映射。  
  
## <a name="see-also"></a>请参阅  
 [教程 4：创建混合应用程序使用 BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)