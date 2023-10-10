# \[React]插槽机制

作用：让组件有强的复用性

-   匿名插槽
-   具名插槽

通过props.children实现

-   示例：逐渐不透明的动画插槽
    ```react&#x20;jsx
    import React from "react";
    //
    import { motion } from "framer-motion";
    //
    /**
     * 逐渐不透明的动画
     *
     * @component ExampleComponent
     * @param {string} title - 逐渐不透明的动画
     * @param {string} content - 逐渐不透明的动画
     * @returns {JSX.Element} - 返回包含标题和内容的 JSX 元素
     */
    //
    export default function Opaque(props) {
      // 我们定义了一个名为 opacityVariants 的对象，其中包含了动画的起始状态和结束状态。
      const opacityVariants = {
        opaque: { opacity: 0 },      // 透明状态
        transparent: { opacity: 1 }, // 不透明状态
      };
      return (
        <motion.div
          variants={opacityVariants}   // 使用定义的动画状态
          initial="opaque"             // 初始状态为不透明
          animate="transparent"        // 动画结束后变为透明
          transition={{ duration: 1.5 }} // 动画过渡时间为1.5秒
        >
          {props.children}
        </motion.div>
      );
    }

    ```

