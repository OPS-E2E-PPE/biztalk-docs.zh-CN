---
title: "元数据和 WCF 服务与 Oracle 数据库的模型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service model, metadata
- WCF client class
- WCF service contract
ms.assetid: b55cf4ed-c41a-4986-bbaf-88e80c32b01f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76933dba64e6e8bb75eb0394ab8e6eedd3fb7116
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-database"></a>元数据和 WCF 服务模型与 Oracle 数据库
在 WCF 服务模型中，你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutile.exe) 生成代理类通过其代码可以：  
  
-   调用适配器 （WCF 客户端类） 上的操作  
  
-   从适配器 （WCF 服务协定） 接收操作  
  
 这些工具生成表示服务协定的操作 （以及支持消息协定、 操作协定和数据协定） 的.NET 类公开的元数据从[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 如需帮助了解此生成结构代码，请参阅"了解生成客户端代码"，网址[http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)。 本主题专门介绍 svcutil.exe 生成，但其内容也是适用于代码的代码，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。 有关如何生成 WCF 客户端类或 WCF 服务约定以目标操作以及 svcutil.exe 之间的差异信息和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[为 Oracle 数据库生成 WCF 客户端或 WCF 服务协定解决方案项目](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
## <a name="see-also"></a>另请参阅  
 [通过使用 WCF 服务模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)