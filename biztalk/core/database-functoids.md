---
title: "数据库 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77bc9390-cdb5-42ff-8b28-6265c51c79fc
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b68a924fba60d4f0162e80dde0ab06b515765558
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="database-functoids"></a>“数据库”Functoid
**数据库**functoid 从在输出实例消息中使用数据库中提取数据。 

## <a name="overview"></a>概述
以下是一份**数据库**functoid 以及如何使用它们：  
  
-   **数据库查找。** 使用**数据库查找**functoid 从数据库中提取信息并将其存储为 Microsoft ActiveX 数据对象.NET (ADO.NET) 记录集。 此 functoid 需要按以下顺序排列的四个输入参数：  
  
    -   查找值  
  
    -   数据库连接字符串  
  
    -   表名  
  
    -   查找值的列名。  
  
-   **错误返回。** 使用**错误返回**functoid 捕获错误的信息，如数据库连接故障，请在运行时期间发生。 此 functoid 需要一个输入的参数： 从链接**数据库查找**functoid。  
  
-   **格式的消息。** 使用参数替换并且可能使用 ID 和值的交叉引用返回格式化的本地化字符串。  
  
-   **获取应用程序 id。** 检索应用程序对象的标识符。  
  
-   **获取应用程序值。** 检索应用程序值。  
  
-   **获取通用的 id。** 检索公用对象标识符。  
  
-   **获取公共值。** 检索公用值。  
  
-   **删除应用程序 id。** 删除应用程序值。  
  
-   **设置常见的 id。** 设置和返回公用对象的标识符。  
  
-   **值提取程序。** 使用**值提取程序**functoid 来提取数据的指定列中返回的记录集从**数据库查找**functoid。 此 functoid 需要两个输入参数： 指向的**数据库查找**functoid 和列名称。  
  
 七个**数据库**functoid-**格式消息，获取应用程序 ID**，**获取应用程序值**，**获取常见 ID**， **获取常见值**，**删除应用程序 ID**，和**设置常见 ID**— 是**CrossReferencing** functoid。 这些 functoid 可以将输入消息中的 ID 和值翻译为输出消息中所需的 ID 和值。 有关详细信息，请参阅**数据库 Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 

## <a name="example"></a>示例  
 下面的示例使用的一些**数据库**functoid。 假设有一个大型零售制造商，在很多地方都设有商店。 若要跟踪的存储，总部，将分配一个唯一的代码调用每个存储**StoreID**。 此外，总部将以下信息与每个相关联**StoreID**:  
  
-   StoreName  
  
-   StoreAddress  
  
-   City  
  
-   PostalCode  
  
-   StorePhoneNumber  
  
-   StoreManager  
  
 这些信息都存储在一个数据库中，并且会定期分发给贸易合作伙伴。 对于该制造商来说，所有采购活动都是总部完成的，而不是各个商店。 当总部向贸易合作伙伴发送采购订单后，一般会有多个商店可以收到通过该采购订单订购的商品。 而不是发送每个存储区中将接收商品的名称和地址信息，只需发送总部**StoreID**。 若要插入高级的发货通知的名称和地址信息，贸易合作伙伴，请使用**数据库**functoid 来自动将此信息插入到输出实例消息。 下图显示了贸易合作伙伴如何在映射中实施 StoreID 替换：  
  
 ![映射显示不同的数据库 functoid。] (../core/media/origdbfunctoids.gif "origdbfunctoids")  
  
 在该图中，源架构代表传入采购订单；目标架构则代表提前发运通知。 **数据库查找**functoid 查找相应的数据库表中相应的记录。 **值提取程序**functoid 从查找记录中提取相应的列。 **错误返回**functoid 在运行时输出一个字符串，包含错误信息，如果没有错误 （如连接失败）。  
  
 在前面的示例中，第一个输入的参数取自**StoreID**字段传入的采购订单，和剩余三个输入的参数是配置中的常量**配置\<Functoid > Functoid**对话框**数据库查找**functoid。 也可以创建源自源架构的链接，以便为全部四个输入参数提供值。  
  
> [!NOTE]
>  * 你无法使用某些 Microsoft SQL Server 数据类型，如**文本**， **ntext**，和**映像**，作为查找值**数据库查找**functoid。 该 functoid 需要可用文本字符串形式表示的数据类型。  
>
>  * 如果没有匹配的输入的参数的多个记录**数据库查找**functoid，**值提取程序**functoid 仅从第一条记录中提取数据。  
>
>  * 在连接字符串中使用 NT 验证可利用加密来保护密码。  

## <a name="available-functoids"></a>可用的 functoid  
 **数据库**functoid 均： 

* 数据库查找
* 错误返回
* 格式化消息
* 获取应用程序 ID
* 获取应用程序值
* 获取公用 ID
* 获取公用值
* 删除应用程序 ID
* 设置公用 ID
* 值提取程序

有关这些 functiods 的更多详细信息，请参阅**Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="see-also"></a>另请参阅  
-  [如何在向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **数据库 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]