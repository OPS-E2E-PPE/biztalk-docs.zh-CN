---
title: SAP 数据提供程序疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, troubleshooting
- troubleshooting, Data Provider for SAP
ms.assetid: 6fe9baed-0404-4f15-b76e-88cc11c5ff46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e0d5406ceb728d28906665fff262edab1623e3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372436"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-sap"></a>SAP 数据提供程序疑难解答
本部分讨论如何使用故障排除技术来解决操作使用时可能遇到的错误[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。  
  
##  <a name="BKMK_SAPUnknownParam"></a> 使用 SAP 数据提供程序的未知的参数错误  
 **问题**  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]时出现以下错误：  
  
```  
Microsoft.Data.SAPClient.SAPException: Failed to retrieve data from SAP server --- > Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Unknown Parameter OUT_ZDATATABLE.  
```  
  
 **原因**  
  
 自定义 RFC、 Z_EXTRACT_DATA_OO，SAP 系统中安装了不是最新版本。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用自定义 RFC，Z_EXTRACT_DATA_OO，来执行 SAP 表的 SELECT 操作。  
  
 **解决方法**  
  
 为可用的最新版本，必须更新自定义 RFC。 此 RFC，Z_EXTRACT_DATA_OO，现 adapterpacknoversion 了。 有关如何安装和卸载自定义 RFC 的详细信息，请参阅[安装适用于 SAP 数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。
  
##  <a name="BKMK_SAPOOM"></a> 内存不足异常时从 SAP 表中选择数据  
 **问题**  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]选择 SAP 系统中的数据时，会引发内存不足异常。  
  
 **原因**  
  
 默认情况下，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]一次检索 10,000 行。 此外，每一批行从 SAP 系统中检索存储在内存中。 因此，  
  
- 如果从中检索数据的表包含大量行，或  
  
- 如果表包含占用大量内存的数据类型的列  
  
  内存使用情况[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]显著增加，可能会导致内存不足异常。  
  
  **解决方法**  
  
  你可以最大的 SAP 系统检索的行数。 您可以通过使用 SELECT 语句中指定 batchsize 选项来实现。 例如：  
  
```  
SELECT * FROM <tablename> OPTION 'batchsize 1000'  
```  
  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]现在一次检索仅 1000年行，并因此不会消耗大量内存。  
  
##  <a name="BKMK_SAPQueryExcep"></a> 执行查询，采用具有日期值的参数时出现异常  
 **问题**  
  
 执行使用 EXECQUERY 命令具有采用日期值参数的查询时出现以下异常：  
  
```  
ErrorCode=RFC_SYS_EXCEPTION. ErrorGroup=RFC_ERROR_SYSTEM_FAILURE.   
SapErrorMessage=Enter date in the format __.__.____.  
```  
  
 **原因**  
  
 在执行时使用 EXECQUERY 命令的查询，始终必须以 YYYYMMDD 格式表示指定日期值。  
  
 **解决方法**  
  
 请确保以 YYYYMMDD 格式表示指定日期值。 例如：  
  
```  
EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1='20080606'  
```  
  
##  <a name="BKMK_SAPNOVARIANT"></a> 执行查询使用 EXECQUERY 命令 NO_VARIANT 异常  
 **问题**  
  
 执行一个查询使用 EXECQUERY 命令时出现以下异常：  
  
```  
Exception: Details: ErrorCode=RFC_EXCEPTION. ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage=NO_VARIANT.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: <RFC name>  
```  
  
 **原因**  
  
 可以有两个可能的原因，此异常：  
  
1. 要执行的查询有 SAP 系统中定义的变体。 变体是指已保存的一组选择条件可以执行 SAP 查询时指定的。 例如，变体可用于指定查询的默认值。  
  
2. 查询尝试执行都不具有 variant 类型的定义，也不需要传递的参数值。  
  
   **解决方法**  
  
3. 对于原因 1，请确保指定的名称与查询关联的变体。 例如：  
  
   ```  
   EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant =  ‘variant1’  
   ```  
  
4. 原因 2，请确保指定的查询命令时提供的虚拟参数名称和值。 例如，如果"myquery"查询不需要任何参数来执行，EXECQUERY 命令必须指定为：  
  
   ```  
   EXECQUERY myquery @usergroup='mygroup',@P1 = 'dummy_value'  
   ```  
  
## <a name="see-also"></a>请参阅  
[SAP 适配器疑难解答](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)