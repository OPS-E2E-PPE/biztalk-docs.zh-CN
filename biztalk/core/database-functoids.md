---
title: 数据库 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77bc9390-cdb5-42ff-8b28-6265c51c79fc
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63709f5857e7d05d4739f5cdcc62916ed5891f9c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389954"
---
# <a name="database-functoids"></a>数据库 Functoid
**数据库**functoid 从输出实例消息中使用的数据库中提取数据。 

## <a name="overview"></a>概述
以下是一系列**数据库**functoid 以及如何使用它们：  

- **数据库查找。** 使用**数据库查找**functoid 从数据库中提取信息并将其存储为 Microsoft ActiveX 数据对象.NET (ADO.NET) 记录集。 此 functoid 需要按以下顺序的四个输入的参数：  

  -   查找值  

  -   数据库连接字符串  

  -   表名称  

  -   查找值的列名称。  

- **错误返回。** 使用**错误返回**functoid 来捕获错误信息，例如数据库连接失败，在运行时出现。 此 functoid 需要一个输入的参数： 从链接**数据库查找**functoid。  

- **格式化消息。** 返回格式化和本地化的字符串，使用参数替换，以及可能的 ID 和值的交叉引用。  

- **获取应用程序 id。** 检索应用程序对象的标识符。  

- **获取应用程序值。** 检索应用程序值。  

- **获取公用 id。** 检索公用对象标识符。  

- **获取公用值。** 检索公用值。  

- **删除应用程序 id。** 删除应用程序值。  

- **设置公用 id。** 设置和返回公用对象标识符。  

- **值提取程序。** 使用**值提取程序**functoid 来提取数据，从指定列中返回的记录集**数据库查找**functoid。 该 functoid 需要两个输入参数： 一个指向**数据库查找**functoid 和列名称。  

  七**数据库**functoid —**格式化消息、 获取应用程序 ID**，**获取应用程序值**，**获取公用 ID**， **获取公用值**，**删除应用程序 ID**，并**设置公用 ID**— 是**CrossReferencing** functoid。 这些 functoid 转换为的 Id 和值从输入消息的 Id 和输出消息中所需值。 有关详细信息，请参阅**Database Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 

## <a name="example"></a>示例  
 下面的示例使用的一些**数据库**functoid。 与存储跨越较大的地理区域，请考虑一个大型零售制造商。 若要跟踪的存储，总部，将分配唯一的代码调用每个应用商店**StoreID**。 此外，总部将以下信息与每个相关联**StoreID**:  

- StoreName  

- StoreAddress  

- City  

- PostalCode  

- StorePhoneNumber  

- StoreManager  

  此信息存储在数据库和分发给贸易合作伙伴定期进行。 对于该制造商来说，所有购买是总部完成的不是各个商店。 当总部向贸易合作伙伴发送采购订单时，很常见的多个商店可以收到通过该采购订单订购的商品。 而不是发送为每个要接收商品的商店名称和地址信息，总部只需发送**StoreID**。 若要提前的发运通知中插入名称和地址信息，贸易合作伙伴可使用**数据库**functoid 以自动将此信息插入到输出实例消息。 下图显示了贸易合作伙伴如何在映射中实施 StoreID 替换。  

  ![将显示不同数据库 functoid 的映射。](../core/media/origdbfunctoids.gif "origdbfunctoids")  

  在图中，源架构代表传入采购订单;目标架构则代表提前的发运通知。 **数据库查找**functoid 查找相应的数据库表中相应的记录。 **值提取程序**functoid 从查找记录中提取相应的列。 **错误返回**functoid 在运行时输出一个字符串，包含错误的信息，如果有错误 （如连接失败）。  

  在上一示例中，第一个输入的参数取自**StoreID**字段传入的采购订单，和剩余三个输入参数中配置的常数**配置\<Functoid\> Functoid**对话框**数据库查找**functoid。 就可以从要为所有四个输入参数提供值的源架构中创建的链接。  

> [!NOTE]
>  * 不能使用某些 Microsoft SQL Server 数据类型，例如**文本**， **ntext**，并**图像**，查找值的形式**数据库查找**functoid。 该 functoid 需要可以表示为文本字符串的数据类型。  
>
>  * 如果没有匹配的输入的参数的多个记录**数据库查找**functoid**值提取程序**functoid 只从第一条记录中提取数据。  
>
>  * 若要保护密码和加密的连接字符串中使用 NT 身份验证。  

## <a name="available-functoids"></a>可用的 functoid  
 **数据库**functoid 包括： 

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

有关这些 functiods 的更多详细信息，请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="see-also"></a>请参阅  
- [如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
- **数据库 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
