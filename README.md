```plantuml
@startuml

abstract class org.rudi.common.storage.entity.AbstractLabelizedEntity <<MappedSuperclass>>  {
	{field} {static} +CODE_COLUMN_LENGTH : int
	{field} {static} +CODE_COLUMN_NAME : String
	{field} +@Column("code") code : String
	{field} +@Column("label") label : String
	{field} {static} -serialVersionUID : long
	{method} +equals ( paramObject1 : Object ) : boolean
	{method} +hashCode () : int
	{method} +toString () : String
}


abstract class org.rudi.common.storage.entity.AbstractLongIdEntity <<MappedSuperclass>>  {
	{field} +@Column("id") @Id id : Long
	{field} {static} -serialVersionUID : long
	{field} +@Column("uuid") uuid : java.util.UUID
	{method} +equals ( paramObject1 : Object ) : boolean
	{method} +hashCode () : int
	{method} +toString () : String
}


abstract class org.rudi.common.storage.entity.AbstractLongIdEntity$AbstractLongIdEntityBuilder {
	{field} -id : Long
	{field} -uuid : java.util.UUID
	{method}  {abstract} +build () : org.rudi.common.storage.entity.AbstractLongIdEntity
	{method} +id ( paramLong1 : Long ) : org.rudi.common.storage.entity.AbstractLongIdEntity$AbstractLongIdEntityBuilder
	{method}  {abstract} #self () : org.rudi.common.storage.entity.AbstractLongIdEntity$AbstractLongIdEntityBuilder
	{method} +toString () : String
	{method} +uuid ( paramUUID1 : java.util.UUID ) : org.rudi.common.storage.entity.AbstractLongIdEntity$AbstractLongIdEntityBuilder
}


abstract class org.rudi.common.storage.entity.AbstractStampedEntity <<MappedSuperclass>>  {
	{field} +@Column("closing_date") closingDate : java.time.LocalDateTime
	{field} +@Column("opening_date") openingDate : java.time.LocalDateTime
	{field} +@Column("order_") order : int
	{field} {static} -serialVersionUID : long
	{method} +equals ( paramObject1 : Object ) : boolean
	{method} +hashCode () : int
	{method} +toString () : String
}


abstract class org.rudi.common.storage.entity.AbstractTranslationEntity <<MappedSuperclass>>  {
	{field} +@Column("lang") lang : String
	{field} {static} -serialVersionUID : long
	{field} +@Column("text") text : String
	{method} +equals ( paramObject1 : Object ) : boolean
	{method} +hashCode () : int
	{method} +toString () : String
}


class org.rudi.common.storage.entity.HibernateEntityHelper {
	{method}  {static} +setCollection ( paramSupplier1 : java.util.function.Supplier , paramCollection2 : java.util.Collection ) : void
}


interface org.rudi.common.storage.entity.PositionedStatus {
	{method}  {abstract} +isFinal () : boolean
	{method}  {abstract} +isInitial () : boolean
}


class org.rudi.common.storage.entity.SkosConceptCodeColumn {
	{field} {static} +LENGTH : int
	{field} {static} +NAME : String
	{field} {static} +TABLE_NAME : String
}


enum org.rudi.common.storage.entity.StatusPosition {
	{field} +FINAL
	{field} +INITIAL
	{field} +INTERMEDIATE
}




org.rudi.common.storage.entity.AbstractLabelizedEntity --|>  org.rudi.common.storage.entity.AbstractLongIdEntity
org.rudi.common.storage.entity.AbstractStampedEntity --|>  org.rudi.common.storage.entity.AbstractLabelizedEntity
org.rudi.common.storage.entity.AbstractTranslationEntity --|>  org.rudi.common.storage.entity.AbstractLongIdEntity

hide methods

@enduml
```
