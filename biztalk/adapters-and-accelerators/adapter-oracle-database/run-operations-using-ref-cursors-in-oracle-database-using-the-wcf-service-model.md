---
title: 使用 WCF 服务模型的 Oracle 数据库中运行的操作使用 REF CURSOR |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations using REF CURSORS
- REF CURSORS, performing operations
ms.assetid: b4cb9ede-eae1-44d7-8ba5-7e1261ccfa3b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c30af70ffe58e1ca8107c07d265e848532e2c768
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990702"
---
# <a name="run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model"></a>使用 WCF 服务模型的 Oracle 数据库中运行的操作使用 REF CURSOR
REF CURSOR 是 Oracle PL/SQL 数据类型对结果集的 Oracle 数据库中表示的指针。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]支持 REF CURSOR 参数在过程、 函数和包。 REF CURSOR 参数可以是强类型化或弱类型具体取决于在过程或函数中的声明。 有关如何通过表示 REF CURSOR 参数的详细说明[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[REF CURSORS 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)。下表总结了如何在 WCF 服务模型中表示 REF CURSOR 参数。  
  
|参数方向|强类型化的 REF CURSOR|弱类型化的 REF CURSOR|  
|-------------------------|--------------------------------|------------------------------|  
|IN|`string [PARAM_NAME]`<br /><br /> 包含一个 PL/SQL 块的字符串。 PL/SQL 块必须返回打开的 REF CURSOR，通过执行"打开为 SELECT"语句或调用函数或过程。 问号 （？） 指示返回参数的 REF CURSOR 的位置。 例如，"开始打开？ 为选择 * 从 MY_TABLE;END"，或"开始 MY_PROC (PARM1，？，PARM2);结束;"。|与强类型相同|  
|OUT|`out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`<br /><br /> 强类型的记录集。|`out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`<br /><br /> 弱类型泛型记录集。|  
|在 OUT|在 OUT REF CURSOR 参数被拆分为 IN 和 OUT 参数。 IN 参数追加在方法签名，以使其不同于 OUT 参数中的"_IN"。 OUT 参数为由强类型的记录集。<br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`|在 OUT REF CURSOR 参数被拆分为 IN 和 OUT 参数。 IN 参数后追加"_IN"以便进行区分的 OUT 参数。 OUT 参数被表示弱类型的记录集。<br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`|  
  
 [PARAM_NAME] = 对 Oracle 数据库; 在函数或过程定义中参数的名称例如，MYREFCURSOR。  
  
 [PROC_NS] = 为包含参数的包、 过程或函数; 而生成的唯一命名空间例如，"microsoft.lobservices.oracledb._2007._03.SCOTT。Package.ACCOUNT_PKG。GET_ACTIVITY"。  
  
 [GENERIC_NS] = 在其中定义该泛型的记录集，该命名空间"microsoft.lobservices.oracledb._2007._03"。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例使用 SCOTT/包/ACCOUNT_PKG Oracle 包。 从 ACCOUNT_PKG 使用以下步骤：  
  
```  
PROCEDURE get_activity(inrecs IN SYS_REFCURSOR, status OUT NUMBER, inoutrecs IN OUT activity_ref_type, outrecs OUT SYS_REFCURSOR);  
```  
  
 使用 SDK 示例提供了一个脚本来生成此包。 有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。  
  
## <a name="ref-cursor-parameters-in-the-wcf-service-model"></a>在 WCF 服务模型中的 REF CURSOR 参数  
 以下示例演示类和 /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY 过程生成的 WCF 客户端。 此过程具有弱类型 IN 和 OUT REF CURSOR 参数，强类型化 IN 出 REF CURSOR 参数。  
  
 以下是方法的在 WCF 客户端以调用 GET_ACTIVITY 中生成的签名。  
  
```  
public System.Nullable<decimal> GET_ACTIVITY(string INRECS, string INOUTRECS_IN, out microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY.INOUTRECSRECORD[] INOUTRECS, out microsoft.lobservices.oracledb._2007._03.GenRecordRow[] OUTRECS);  
```  
  
 在中**GET_ACTIVITY**方法，在 OUT 参数 INOUTRECS 拆分为两个参数：  
  
- INOUTRECS_IN 是一个字符串，表示在 REF CURSOR 参数。  
  
- INOUTRECS 是表示一个 OUT REF CURSOR 参数，强类型化记录集。  
  
  弱类型化 OUT 参数，OUTRECS，表示为泛型的记录集。 弱类型参数，INRECS 中, 表示为一个字符串。  
  
### <a name="strongly-typed-out-ref-cursor-parameters"></a>强类型扩展的 REF CURSOR 参数  
 强类型化扩展 （或在缩减） 在基于架构、 包和过程或函数使用它们的名称的唯一命名空间中生成 REF CURSOR 参数。 有关 /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY 过程中，此命名空间是`microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`。 由具有"记录"的参数名称构成的类名和类组成表示 Oracle 字段的属性。 下面显示了表示 INOUTRECS REF CURSOR 参数生成的强类型记录的类的一部分。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class INOUTRECSRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        ...  
  
        private System.Nullable<decimal> TIDField;  
  
        ...  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public System.Nullable<decimal> TID {  
            get {  
                return this.TIDField;  
            }  
            set {  
                this.TIDField = value;  
            }  
        }  
  
        ...  
  
    }  
}  
```  
  
### <a name="weakly-typed-out-ref-cursor-parameters"></a>弱类型扩展的 REF CURSOR 参数  
 弱类型扩展 （或在缩减） REF CURSOR 参数表示通过通用记录类。 泛型的记录集始终生成相同的命名空间，并且具有相同的类名，而不考虑函数或过程。 下面的代码演示通用记录类**microsoft.lobservices.oracledb._2007._03.GenRecordRow**，它表示 OUTRECS 出 SYS_REFCURSOR 参数 （弱类型化） 的记录。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03 {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class GenRecordRow : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private microsoft.lobservices.oracledb._2007._03.GenRecordColumn[] GenRecordColumnField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public microsoft.lobservices.oracledb._2007._03.GenRecordColumn[] GenRecordColumn {  
            get {  
                return this.GenRecordColumnField;  
            }  
            set {  
                this.GenRecordColumnField = value;  
            }  
        }  
    }  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class GenRecordColumn : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private string ColumnNameField;  
  
        private string ColumnValueField;  
  
        private string ColumnTypeField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true, EmitDefaultValue=false)]  
        public string ColumnName {  
            get {  
                return this.ColumnNameField;  
            }  
            set {  
                this.ColumnNameField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public string ColumnValue {  
            get {  
                return this.ColumnValueField;  
            }  
            set {  
                this.ColumnValueField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true, EmitDefaultValue=false, Order=2)]  
        public string ColumnType {  
            get {  
                return this.ColumnTypeField;  
            }  
            set {  
                this.ColumnTypeField = value;  
            }  
        }  
    }  
}  
```  
  
## <a name="using-ref-cursor-parameters-with-a-wcf-client"></a>使用 WCF 客户端使用 REF CURSOR 参数  
 若要通过使用 WCF 客户端调用过程或函数的 REF CURSOR 参数，请执行以下操作：  
  
1. 将字符串传递中的 for each 或 IN 出 REF CURSOR 参数，其中包含 PL/SQL 阻止打开 REF CURSOR。 此块可以执行一个打开的 SELECT 语句，或调用的函数或在 OUT 参数返回打开的 REF CURSOR 的过程。  
  
2. 过程或函数返回时，对操作中的任何 OUT 或 IN 出 REF CURSOR 参数所返回的记录集的数据。 通用记录为弱类型化 REF CURSOR 参数设置或强类型的记录集的强类型化 REF CURSOR 参数，将记录集。  
  
   有关如何使用 WCF 服务模型调用过程和函数的详细信息，请参阅[调用的函数和使用 WCF 服务模型的 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)。  
  
   下面的示例调用 GET_ACTIVITY 过程。 它演示了这两种指定 IN REF CURSOR 参数：  
  
- 对于在 REF CURSOR 参数，一个打开的 SELECT 语句指定要为帐户 100001 返回活动。  
  
- 对于在 OUT REF CURSOR 参数，调用该 /SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY 过程。 此过程将打开包含所有 ACCOUNTACTIVITY 表中的活动并将其作为一个输出参数返回 REF CURSOR。  
  
  该示例还演示如何读取从记录集的强类型化和弱类型化 REF CURSOR 参数返回的数据。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF LOB Adapter SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// namespaces for strongly-typed and weakly typed REF CURSOR records  
using GET_ACTIVITYns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY;  
using GENERICns = microsoft.lobservices.oracledb._2007._03;  
  
// In this sample, INRECS is opened by using an OPEN FOR statement, and  
// INOUTRECS_IN is opened by calling the GET_ALL_ACTIVITY procedure on Oracle.  
  
namespace OracleRefCursorsSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create the client  
            SCOTTPackageACCOUNT_PKGClient accountPkgClient =   
                new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG");  
            // Set credentials  
            accountPkgClient.ClientCredentials.UserName.UserName = "SCOTT";  
            accountPkgClient.ClientCredentials.UserName.Password = "TIGER";  
  
            try  
            {  
  
                GET_ACTIVITYns.INOUTRECSRECORD[] strongCursor;  
                GENERICns.GenRecordRow[] weakCursor;  
  
                Console.WriteLine("Opening client");  
                // Open the client  
                accountPkgClient.Open();  
  
                Console.WriteLine("Invoking ACCOUNT_PKG.GET_ACTIVITY");  
                // Get  ACCOUNTACTIVITY records  
                // The IN REF CURSOR is set to all activity for account 100001  
                // The input part of the IN OUT ref cursor calls GET_ALL_ACTIVITY  
                // The weakly-typed OUT REF CURSOR parameter returns a list of activity for account 100001  
                // The strongly-typed IN OUT REF CURSOR parameter returns a list of all activity  
                string inRecsString = "BEGIN OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY WHERE ACCOUNT=100001; END;";  
                string inoutRecsString = "BEGIN ACCOUNT_PKG.GET_ALL_ACTIVITY(?); END;";  
  
                accountPkgClient.GET_ACTIVITY(  
                                inRecsString,  
                                inoutRecsString,  
                                out strongCursor,  
                                out weakCursor);  
  
                // Display strong ref cursor (all activity)  
                Console.WriteLine("\nList of all activity returned (strong ref cursor)");  
                Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
                for (int i = 0; i < strongCursor.Length; i++)  
                {  
                    Console.WriteLine("{0}\t{1}\t{2:C}\t{3}\t{4}",strongCursor[i].TID,  
                        strongCursor[i].ACCOUNT,   
                        strongCursor[i].AMOUNT,   
                        strongCursor[1].TRANSDATE,  
                        strongCursor[i].DESCRIPTION);  
                }  
  
                // Display weak ref cursor (account 100001)  
                Console.WriteLine("\nList of activity for account 100001 returned (weak ref cursor)");  
                Console.WriteLine("Tx Id\tAmount\tDate\t\t\tDescription");  
                for (int i = 0; i < weakCursor.Length; i++)  
                {  
                    Console.WriteLine("{0}\t{1:C}\t{2}\t{3}", weakCursor[i].GenRecordColumn[0].ColumnValue,  
                        weakCursor[i].GenRecordColumn[2].ColumnValue,  
                        weakCursor[i].GenRecordColumn[4].ColumnValue,  
                        weakCursor[i].GenRecordColumn[3].ColumnValue);  
                }  
  
                Console.WriteLine("\nHit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw ex;  
            }  
            finally  
            {  
                // Close the client  
                accountPkgClient.Close();  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle 数据库应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)