---
title: 元数据和 WCF 服务模型与 Oracle E-business Suite |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95d3fcba-c72f-4ae9-82bd-abbfc2a0c2c4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cf87c0a579d1f0c0de590d78e559ead73be0cec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215205"
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-e-business-suite"></a>元数据和 Oracle E-business Suite WCF 服务模型
在 WCF 服务模型中，你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutile.exe) 来执行以下操作：  
  
-   生成服务协定 — WCF 服务协定-通过它你的代码可以从适配器接收操作。 此.NET 接口表示目标操作的服务协定。  
  
-   生成代理类-WCF 客户端类-你的代码可以通过该调用在适配器上的操作。  
  
-   表示支持消息协定、 操作协定和服务协定的数据协定的带批注的类。  
  
 如需帮助了解此生成结构代码，请参阅"了解生成客户端代码"，网址[http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)。 本主题专门介绍 svcutil.exe 生成，但其内容也是适用于代码的代码，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。  
  
 有关如何生成 WCF 客户端类或 WCF 服务约定以目标操作以及 svcutil.exe 之间的差异信息和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 WCF 服务协定为 Oracle E-business套件解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  
  
## <a name="see-also"></a>另请参阅  
 [通过使用 WCF 服务模型开发 Oracle E-business Suite 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)