# Look and Feel - Java Swing UI Theming 🎨

## 📌 Sobre o Projeto

Experimentos com diferentes Look and Feel (temas visuais) para aplicações Java Swing. Demonstra como aplicar e customizar a aparência de interfaces gráficas Java.

## 🎯 Objetivo

Explorar diferentes opções de Look and Feel em Java:
- Look and Feel nativo do sistema
-Themes de terceiros (Nimbus, FlatLaf, etc)
- Customização de cores e estilos
- Comparação visual entre temas

## 🚀 Tecnologias Utilizadas

- **Java** - Linguagem de programação
- **Swing** - Framework GUI
- **LookAndFeel API** - Sistema de temas

## 📁 Estrutura do Projeto

```
look-and-feel/
├── src/                    # Código-fonte Java
│   ├── Main.java           # Aplicação principal
│   ├── LafDemo.java        # Demonstração de temas
│   └── ...                 # Outros componentes
└── README.md
```

## 🎨 Look and Feel Disponíveis

### Nativos do Java

1. **Metal** (padrão do Java)
2. **Nimbus** (moderno, gradientes)
3. **Motif** (CDE/Motif)
4. **Windows** (estilo Windows - somente Windows)
5. **Windows Classic** (Windows 95/98)
6. **Mac** (estilo macOS - somente macOS)
7. **GTK+** (estilo Linux GTK - somente Linux)

### Terceiros Populares

1. **FlatLaf** - Flat, moderno, dark mode
2. **Darcula** - Dark theme (IntelliJ)
3. **JTattoo** - Vários temas
4. **WebLaf** - Modern web-inspired
5. **Substance** - Temas sofisticados

## 🔧 Funcionalidades

- ✅ Galeria de Look and Feel
- ✅ Troca de tema em runtime
- ✅ Demonstração de todos os componentes Swing
- ✅ Comparação visual lado a lado
- ✅ Customização de cores
- ✅ Salvar preferências de tema

## 💻 Como Usar

### Pré-requisitos

- **JDK 8+**
- **Maven** ou **Gradle** (para dependências de terceiros)

### Compilação e Execução

### Opção 1: Linha de Comando

```bash
# Compilar
javac -d bin src/**/*.java

# Executar
java -cp bin Main
```

### Opção 2: Com Maven

```bash
# Build
mvn clean compile

# Executar
mvn exec:java -Dexec.mainClass="Main"

# Empacotar com dependências
mvn clean package assembly:single
```

### Opção 3: Com Gradle

```bash
# Build
gradle build

# Executar
gradle run

# JAR executável
gradle jar
```

### Com Maven

```xml
<dependencies>
    <!-- FlatLaf -->
    <dependency>
        <groupId>com.formdev</groupId>
        <artifactId>flatlaf</artifactId>
        <version>3.2.5</version>
    </dependency>
    
    <!-- JTattoo -->
    <dependency>
        <groupId>com.jtattoo</groupId>
        <artifactId>JTattoo</artifactId>
        <version>1.6.13</version>
    </dependency>
</dependencies>
```

## 📚 Exemplos de Uso

### 1. Aplicar Metal (Padrão)

```java
import javax.swing.*;

public class Main {
    public static void main(String[] args) {
        try {
            UIManager.setLookAndFeel(
                UIManager.getCrossPlatformLookAndFeelClassName()
            );
        } catch (Exception e) {
            e.printStackTrace();
        }
        
        SwingUtilities.invokeLater(() -> {
            JFrame frame = new JFrame("Look and Feel Demo");
            // ...
        });
    }
}
```

### 2. Aplicar Nimbus

```java
try {
    for (UIManager.LookAndFeelInfo info : UIManager.getInstalledLookAndFeels()) {
        if ("Nimbus".equals(info.getName())) {
            UIManager.setLookAndFeel(info.getClassName());
            break;
        }
    }
} catch (Exception e) {
    e.printStackTrace();
}
```

### 3. Aplicar Look and Feel Nativo do Sistema

```java
try {
    UIManager.setLookAndFeel(
        UIManager.getSystemLookAndFeelClassName()
    );
} catch (Exception e) {
    e.printStackTrace();
}
```

### 4. Aplicar FlatLaf Dark

```java
import com.formdev.flatlaf.FlatDarkLaf;

public class Main {
    public static void main(String[] args) {
        FlatDarkLaf.setup();
        
        SwingUtilities.invokeLater(() -> {
            // Criar UI
        });
    }
}
```

### 5. Trocar Look and Feel em Runtime

```java
private void changeLookAndFeel(String lafClassName) {
    try {
        UIManager.setLookAndFeel(lafClassName);
        SwingUtilities.updateComponentTreeUI(frame);
        frame.pack();
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

### 6. Customizar Cores

```java
// Antes de criar componentes
UIManager.put("Button.background", Color.BLUE);
UIManager.put("Button.foreground", Color.WHITE);
UIManager.put("Panel.background", new Color(240, 240, 240));
UIManager.put("TextField.background", Color.WHITE);
```

## 📋 Demo de Componentes

A aplicação demonstra os seguintes componentes:

- **JButton** - Botões
- **JTextField, JTextArea** - Campos de texto
- **JComboBox** - Drop-down
- **JList** - Listas
- **JTree** - Árvores
- **JTable** - Tabelas
- **JScrollBar, JScrollPane** - Scroll
- **JTabbedPane** - Abas
- **JMenuBar, JMenu** - Menus
- **JProgressBar** - Barra de progresso
- **JSlider** - Slider
- **JCheckBox, JRadioButton** - Seleção

## 📊 Comparação de Temas

| Theme | Visual | Dark Mode | Customizável | Performance |
|-------|--------|-----------|----------------|-------------|
| Metal | Clássico | ❌ | ✅✅ | ✅✅✅ |
| Nimbus | Moderno | ❌ | ✅✅✅ | ✅✅ |
| System | Nativo | Varia | ❌ | ✅✅✅ |
| FlatLaf | Flat | ✅ | ✅✅✅ | ✅✅✅ |
| Darcula | Dark | ✅ | ✅✅ | ✅✅ |
| JTattoo | Rico | ✅ | ✅✅✅ | ✅ |

## 🔗 Referências

- [Oracle - Look and Feel](https://docs.oracle.com/javase/tutorial/uiswing/lookandfeel/)
- [FlatLaf](https://www.formdev.com/flatlaf/)
- [JTattoo](http://www.jtattoo.net/)
- [Substance](https://github.com/kirill-grouchnikov/radiance)
- [UIManager API](https://docs.oracle.com/javase/8/docs/api/javax/swing/UIManager.html)

## 💡 Conceitos Demonstrados

- **UIManager**: Gerenciamento global de Look and Feel
- **Pluggable Look and Feel (PLAF)**: Arquitetura de temas do Swing
- **SwingUtilities.updateComponentTreeUI()**: Atualização dinâmica
- **UIDefaults**: Customização de propriedades visuais
- **Runtime theme switching**: Troca de temas sem reiniciar

## ⚙️ Melhorias Implementadas

### ✅ Configuração
- **EditorConfig** adicionado para encoding UTF-8
- Indentação Java configurada (tabs, 4 espaços)

### ✅ Documentação
- README expandido com 6 exemplos de código
- Múltiplas opções de build (Maven, Gradle, CLI)
- Tabela comparativa de temas
- Dependências Maven atualizadas (FlatLaf 3.2.5, JTattoo 1.6.13)
- Lista completa de componentes demonstrados
- Customização de cores explicada
- Runtime theme switching documentado

## 🚀 Melhorias Futuras

- [ ] Interface gráfica para seleção de temas
- [ ] Salvar preferências do usuário
- [ ] Preview lado a lado de múltiplos temas
- [ ] Export de configuração customizada
- [ ] Suporte para temas personalizados
- [ ] Integração com JavaFX (via JFXPanel)

## 👨‍💻 Autor

Claudio Almeida

## 📝 Licença

Projeto educacional.

---

> **Dica**: Para aplicações modernas, considere JavaFX ou frameworks web para UI mais flexíveis.

