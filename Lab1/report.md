```
classDiagram
direction LR

class Flag {
  <<interface>>
  +description() str
  +emoji() str
}

class Anthem {
  <<interface>>
  +title() str
}

class Capital {
  <<interface>>
  +name() str
  +population() int
}

class CountryFactory {
  <<interface>>
  +create_flag() Flag
  +create_anthem() Anthem
  +create_capital() Capital
}

class SimpleFlag {
  -description_text: str
  -emoji_text: str
  +description() str
  +emoji() str
}

class SimpleAnthem {
  -anthem_title: str
  +title() str
}

class SimpleCapital {
  -city_name: str
  -estimated_population: int
  +name() str
  +population() int
}

class RussiaFactory
class ChinaFactory
class IndiaFactory

Flag <|.. SimpleFlag
Anthem <|.. SimpleAnthem
Capital <|.. SimpleCapital

CountryFactory <|.. RussiaFactory
CountryFactory <|.. ChinaFactory
CountryFactory <|.. IndiaFactory

CountryFactory ..> Flag   : creates
CountryFactory ..> Anthem : creates
CountryFactory ..> Capital: creates

```