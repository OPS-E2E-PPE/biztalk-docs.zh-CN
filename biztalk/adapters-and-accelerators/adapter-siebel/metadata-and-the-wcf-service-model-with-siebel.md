---
title: 元数据和 WCF 服务模型与 Siebel |Microsoft Docs
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
ms.openlocfilehash: 73fdf3b57756bb2dfc007e63f803bf17c29285ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976646"
---
# <a name="metadata-and-the-wcf-service-model-with-siebel"></a>元数据和具有 Siebel 的 WCF 服务模型
在 WCF 服务模型，可使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutile.exe) 生成代理类，WCF 客户端类，通过该代码可以调用操作上[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。  
  
 这些工具使用由适配器公开的元数据来生成：  
  
- 一个表示目标操作的服务协定的带批注的.NET 接口。 此接口被调用 WCF 服务约定。  
  
- 表示支持消息协定、 操作约定和服务协定的数据协定的带批注的类。  
  
- WCF 客户端类的方法可用于调用服务方法 （操作） 公开的 WCF 服务约定。  
  
  有关帮助理解此生成的结构代码，请参阅"了解生成客户端代码"，网址[ http://go.microsoft.com/fwlink/?LinkId=98365 ](http://go.microsoft.com/fwlink/?LinkId=98365)。 本主题专门介绍代码 svcutil.exe 生成，但其内容也是适用于代码的[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。  
  
  有关如何生成目标的操作的 WCF 客户端类以及 svcutil.exe 之间的差异信息并[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 WCF 的服务约定以用于 Siebel 解决方案项目](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
## <a name="see-also"></a>请参阅  
 [开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)