class SlideRail:
    def __init__(self, length):
        self.length = length  # 滑軌的總長度
        self.position = 0  # 物體在滑軌上的當前位置
        self.speed = 0  # 物體的移動速度
    
    def set_speed(self, speed):
        """設定滑動速度"""
        self.speed = speed
        print(f"Speed set to {self.speed} units per second.")

    def move(self, time):
        """讓物體根據速度和時間移動"""
        movement = self.speed * time
        new_position = self.position + movement
        
        # 確保物體不會移動超出滑軌的範圍
        if new_position > self.length:
            self.position = self.length
            print(f"Reached the end of the rail at position {self.length}.")
        elif new_position < 0:
            self.position = 0
            print("Reached the start of the rail at position 0.")
        else:
            self.position = new_position
            print(f"Object moved to position {self.position}.")

    def stop(self):
        """停止移動"""
        self.speed = 0
        print("Object has stopped moving.")

# 創建一個長度為100單位的滑軌
rail = SlideRail(100)

# 設置速度並讓物體移動
rail.set_speed(10)  # 設置速度為10單位/秒
rail.move(5)  # 讓物體滑動5秒
rail.move(10)  # 再移動10秒

# 停止物體運動
rail.stop()
# sliderail
