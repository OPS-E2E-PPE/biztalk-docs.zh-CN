---
title: 在 Oracle 数据库中使用 WCF 服务模型运行 SQLEXECUTE 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, performing a SQLEXECUTE operation
- SQLEXECUTE operation, performing a
- how to, invoke the SQLEXECUTE operation
ms.assetid: d3f61e5f-4453-4a76-9bc6-40d91cb58224
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2aedcd9874682ed71af774db72979c152836ab3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004848"
---
# <a name="run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model"></a>在 Oracle 数据库中使用 WCF 服务模型运行 SQLEXECUTE 操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]显示一组标准的 Oracle 数据库项目上的操作。 通过使用这些操作，可以执行诸如调用 Oracle 函数或过程，或执行对表的基本 SQL 数据操作语言 (DML) 操作。 但是，可能有需要你执行操作的方案由您的业务逻辑驱动的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不能显示。 例如，您可能希望：  
  
- 不显示的数据库项目上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; 例如，获取 CURVAL 或 NEXTVAL Oracle 序列。  
  
- 执行数据定义语言操作;例如，创建一个表。  
  
- 如果没有安装在设计时用于数据库项目上执行操作例如，更新您的业务逻辑创建一个临时表中的记录。  
  
- 执行更复杂的表比操作的 DML 操作的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]显示; 例如，若要执行查询，包括对 JOIN 子句。  
  
  对于这些类型的情况下， [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] SQLEXECUTE 操作的图面。 通过使用 SQLEXECUTE 操作，可以对 Oracle 数据库执行参数化的 SQL 语句。 SQLEXECUTE 操作支持的输入的参数块组成，您可以执行一次为每个集的同一 SQL 语句的参数集。 SQLEXECUTE 操作返回中泛型的记录集的 SQL 语句的结果。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题使用 Oracle 序列中的示例名为 TID_SEQ。 使用 SDK 示例提供了一个脚本来生成此序列。 有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 WCF 服务模型生成专用的 WCF 客户端**SQLEXECUTEClient**，SQLEXECUTE 操作的。 下面的代码演示**SQLEXECUTEClient**和调用来调用 SQLEXECUTE 操作的方法的签名。  
  
```  
public partial class SQLEXECUTEClient : System.ServiceModel.ClientBase<SQLEXECUTE>, SQLEXECUTE {  
  
    ...  
  
    public microsoft.lobservices.oracledb._2007._03.GenRecordRow[] SQLEXECUTE(string SQLSTATEMENT, string PARAMETERSCHEMA, microsoft.lobservices.oracledb._2007._03.PARAMETERDATA[] PARAMETERSET);   
}  
```  
  
 SQLEXECUTE 操作将返回通用的记录集。 此记录集包含的值 （如果有） 返回的语句执行该 SQLEXECUTE 操作。 可以向其中每个包含一系列表示为字符串的输入参数 PARAMETERDATA 对象的集合中的 SQLEXECUTE 操作传递输入参数的集。 下面的代码演示 PARAMETERDATA 集的定义。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03 {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class PARAMETERDATA : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        ...  
  
        private string[] PARAMETERField;  
  
        ...  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public string[] PARAMETER {  
            get {  
                return this.PARAMETERField;  
            }  
            set {  
                this.PARAMETERField = value;  
            }  
        }  
    }  
}  
```  
  
## <a name="invoking-the-sqlexecute-operation"></a>调用 SQLEXECUTE 操作  
 若要通过使用 WCF 客户端调用 SQLEXECUTE 操作，请执行以下步骤。  
  
1. 生成**SQLEXECUTEClient**类为目标表或视图。  
  
   > [!IMPORTANT]
   >  SQLEXECUTE 操作显示在根节点下 (**/**) 中**选择一个类别**窗格中的**添加适配器服务引用**对话框。  
  
2. 创建的实例**SQLEXECUTEClient**类，并调用**SQLEXECUTE**要对 Oracle 数据库执行 SQL 语句的方法。  
  
   有关更多详细信息，有关如何创建 WCF 客户端类，并在调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[与 Oracle 数据库适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)。  
  
   下面的示例使用**SQLEXECUTEClient**若要获取 Oracle 序列，TID_SEQ，下一个值，通过执行以下 SQL 语句： `SELECT tid_seq.nextval id from DUAL`。 然后向控制台写入输出。  
  
```  
using (SQLEXECUTEClient sqlClient = new SQLEXECUTEClient("OracleDBBinding_SQLEXECUTE"))  
{  
    sqlClient.ClientCredentials.UserName.UserName = "SCOTT";  
    sqlClient.ClientCredentials.UserName.Password = "TIGER";  
    try  
    {  
        sqlClient.Open();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error opening SQL client " + ex.Message);  
        throw;  
    }  
    microsoft.lobservices.oracledb._2007._03.GenRecordRow[] sequenceRec =   
        new microsoft.lobservices.oracledb._2007._03.GenRecordRow[0];  
  
    try  
    {  
        sequenceRec = sqlClient.SQLEXECUTE("SELECT tid_seq.nextval id from DUAL", null, null);  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error executing SQL client " + ex.Message);  
        throw;  
    }  
  
    if (sequenceRec.Length > 0)  
    {  
        Console.WriteLine("TID_SEQUENCE value is {0}", sequenceRec[0].GenRecordColumn[0].ColumnValue);  
    }  
    else  
    {  
    Console.WriteLine("Couldn't get next TID_SEQUENCE value");  
    }  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle 数据库应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)