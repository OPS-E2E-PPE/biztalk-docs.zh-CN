---
title: 解决问题的数据提供程序 Siebel |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, troubleshooting
- troubleshooting, Data Provider for Siebel
ms.assetid: 2bfe69a2-d6de-466d-9f36-f11c386c771c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae6e100635b1cb2db5c78ff713c8e6ad32d4e7d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221997"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-siebel"></a>解决与用于 Siebel 的数据提供程序的问题
本部分讨论如何使用故障排除方法来解决在使用时可能遇到的错误[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。  
  
## <a name="known-issues"></a>已知问题  
  
### <a name="data-provider-for-siebel-may-give-component-datareader-source-380-error"></a>用于 Siebel 数据提供程序都可能导致"组件 DataReader 源 (380)"错误  
 **问题**  
  
 Siebel 在业务组件，对执行 SELECT 查询时[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]都可能导致"组件 DataReader 源 (380)"错误。  
  
 **可能的原因**  
  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使此错误，如果收到 Siebel 系统的参数的值超出了参数的 maxLength 属性。  
  
## <a name="see-also"></a>另请参阅  
[解决在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)