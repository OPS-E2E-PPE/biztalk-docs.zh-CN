---
title: ExportParties 命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b421c8ed-d505-48ba-9d1d-8519c9d51750
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca525872ccc1cd941673189c4ac176fc4631f22
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245813"
---
# <a name="exportparties-command"></a>ExportParties 命令
导出到 XML 绑定文件的所有方和协议。

> [!IMPORTANT]
> 此命令是新开头 **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，和任何更高版本。

## <a name="usage"></a>用法
  **BTSTask ExportParties-目标**:*值*[**-服务器**:*值*] [**-数据库**:*值*]
  
## <a name="parameters"></a>Parameters

|参数|必需|值|  
|---|---|---|  
| **-目标** | 必需 | 要写入的 XML 绑定文件的路径和文件名称。 |
| **服务器** | 可选 | 承载 BizTalk 配置数据库的 SQL server 的名称。 |
| **数据库** | 可选 | BizTalk 配置数据库的名称。|

## <a name="sample"></a>示例
  `ExportParties  -Destination:"C:\Temp\MyParties.Xml"` 

## <a name="remarks"></a>注释
  导出仅方、 协议和 EDI 回退设置。 不导出任何应用程序项目。
