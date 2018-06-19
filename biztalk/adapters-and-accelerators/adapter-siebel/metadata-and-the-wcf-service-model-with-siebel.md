---
title: 元数据和 WCF 服务模型与 Siebel |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, metadata
- metadata, and the WCF service model
ms.assetid: 3aca1835-fb9e-4841-a920-078da0b3fe76
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed348c2ab183960b7af1383768259f67c4ca6270
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221893"
---
# <a name="metadata-and-the-wcf-service-model-with-siebel"></a>元数据和 Siebel WCF 服务模型
在 WCF 服务模型中，你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutile.exe) 若要生成的代理类-WCF 客户端类 — 通过其代码可以调用操作上[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。  
  
 这些工具使用适配器公开的元数据来生成：  
  
-   表示目标操作的服务协定的.NET 批注的接口。 此接口称为 WCF 服务协定。  
  
-   表示支持消息协定、 操作协定和服务协定的数据协定的带批注的类。  
  
-   WCF 客户端类，可以使用其方法来调用由 WCF 服务协定公开的服务方法 （操作）。  
  
 如需帮助了解此生成结构代码，请参阅"了解生成客户端代码"，网址[http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)。 本主题专门介绍 svcutil.exe 生成，但其内容也是适用于代码的代码，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。  
  
 有关如何生成 WCF 客户端类，以便使用目标操作以及 svcutil.exe 之间的差异信息和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 WCF 的服务协定为 Siebel 解决方案项目](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
## <a name="see-also"></a>另请参阅  
 [开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)