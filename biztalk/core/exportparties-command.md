---
title: ExportParties 命令 |Microsoft Docs
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
ms.openlocfilehash: 63245cf72306af5bb4c28552a037ce89d8e6bfe8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345915"
---
# <a name="exportparties-command"></a>ExportParties 命令
将所有参与方和协议导出到 XML 绑定文件。

> [!IMPORTANT]
> 此命令将新开头**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**，和任何更高版本。

## <a name="usage"></a>用法
  **BTSTask ExportParties-目标**:*值*[**-Server**:*值*] [**-数据库**:*值*]
  
## <a name="parameters"></a>Parameters

|参数|Required|ReplTest1|  
|---|---|---|  
| **-Destination** | Required | 要写入的 XML 绑定文件的路径和文件名称。 |
| **-Server** | 可选 | 承载 BizTalk 配置数据库的 SQL server 的名称。 |
| **-Database** | 可选 | BizTalk 配置数据库的名称。|

## <a name="sample"></a>示例
  `ExportParties  -Destination:"C:\Temp\MyParties.Xml"` 

## <a name="remarks"></a>备注
  导出的参与方、 协议和 EDI 回退设置。 导出无应用程序项目。
