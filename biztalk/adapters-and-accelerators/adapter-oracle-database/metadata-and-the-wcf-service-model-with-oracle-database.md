---
title: 元数据和 WCF 服务模型与 Oracle 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service model, metadata
- WCF client class
- WCF service contract
ms.assetid: b55cf4ed-c41a-4986-bbaf-88e80c32b01f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3b1c3eed2ab71282a50ccbb6709601aa69ca733
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973294"
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-database"></a>元数据和具有 Oracle 数据库的 WCF 服务模型
在 WCF 服务模型，可使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutile.exe) 生成代理类通过它你代码可能是：  
  
- 调用适配器 （WCF 客户端类） 上的操作  
  
- 从适配器 （WCF 服务约定） 接收操作  
  
  这些工具生成表示目标操作 （以及支持消息协定、 操作约定和数据协定） 的服务约定的.NET 类公开的元数据从[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 有关帮助理解此生成的结构代码，请参阅"了解生成客户端代码"，网址[ http://go.microsoft.com/fwlink/?LinkId=98365 ](http://go.microsoft.com/fwlink/?LinkId=98365)。 本主题专门介绍代码 svcutil.exe 生成，但其内容也是适用于代码的[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。 有关如何生成 WCF 客户端类或目标的操作的 WCF 服务协定和 svcutil.exe 之间的差异信息并[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[为 Oracle 数据库生成 WCF 客户端或 WCF 服务约定解决方案项目](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 WCF 服务模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)