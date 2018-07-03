---
title: 元数据和具有 SQL 适配器的 WCF 服务模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4353ce67-f0e8-4f96-b1d9-95deeee7f3e6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfc6e490b2966a0b68d1a9c8669cf4601881743e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008222"
---
# <a name="metadata-and-the-wcf-service-model-with-the-sql-adapter"></a>元数据和具有 SQL 适配器的 WCF 服务模型
在 WCF 服务模型，可使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutile.exe) 来执行以下操作：  
  
- 生成服务协定，WCF 服务约定，通过该代码可以从适配器接收操作。 此.NET 接口表示目标操作的服务协定。  
  
- 生成代理类，WCF 客户端类，通过该代码可以调用在适配器上的操作。  
  
- 表示支持消息协定、 操作约定和服务协定的数据协定的带批注的类。  
  
  了解此生成的代码的结构的帮助，请参阅[了解生成的客户端代码](https://msdn.microsoft.com/library/ms733881.aspx)。 本主题专门介绍代码 svcutil.exe 生成，但其内容也是适用于代码的[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。  
  
  有关如何生成 WCF 客户端类或目标的操作的 WCF 服务协定和 svcutil.exe 之间的差异信息并[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)