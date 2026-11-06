pipeline {
agent any
stages {
stage(&#39;Checkout&#39;) {
steps {
checkout scm
}
}
stage(&#39;Build&#39;) {
steps {

sh &#39;mvn clean compile&#39;
}
}
stage(&#39;Test&#39;) {
steps {
sh &#39;mvn test&#39;
}
}
stage(&#39;Package&#39;) {
steps {
sh &#39;mvn package&#39;
}
}
}
}
