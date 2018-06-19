---
title: ImportSettings 命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 587f7e1f-9cf7-4e7b-90cd-11a266f474dc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c609634422f8c8b5f2c1a96691fe4eda708e5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257549"
---
# <a name="importsettings-command"></a>ImportSettings 命令
将 BizTalk 组、主机或主机实例设置从 XML 源文件导入到配置数据库。 设置将按照映射 XML 文件中的方式进行映射。 这些设置可能已导出中所述[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)或[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此操作，你必须作为 BizTalk Server Administrators 组的成员身份登录。  
  
## <a name="usage"></a>用法  
 `ImportSettings –Source:value –Map: value [-Server:value] [-Database:value]`  
  
## <a name="parameters"></a>Parameters  
  
|**参数**|必需|值|  
|-------------------|--------------|-----------|  
|**源代码**|是|导出的设置 XML 文件的路径和文件名。|  
|**映射**|是|映射 XML 文件的路径和文件名。|  
|**服务器**|可选|托管 BizTalk 配置数据库的 SQL 服务器计算机名称。|  
|**数据库**|可选|BizTalk 配置数据库的名称。|  
  
## <a name="sample"></a>示例  
 `BTSTask ImportSettings /Source:”C:\My Folder>\ExportedSettings.xml” /Map:Mappings.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)