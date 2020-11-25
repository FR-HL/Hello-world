import builtins
class Person:
    def __init__(self, name):
        #姓名
        self.name = name
        # 血量
        self.blood = 100

    # 给弹夹安装子弹
    def install_bullet(self, clip, bullet):

        # 弹夹放置子弹
        clip.save_bullets(bullet)


# 给枪安装弹夹
def install_clip(self, gun, clip):
    # 枪链接弹夹
    gun.mounting_clip(clip)
    # 持枪


def take_gun(self, gun):
    self.gun = gun
    # 射击敌人
    self.gun.shoot(enemy)


def __str__(self):
    return self.name + "剩余血量为：" + str(self.blood)


# 掉血
def lose_blood(self, damage):
    self.boold -= damage


# 定义表示弹夹的类
class Clip:
    def __init__(self, capacity):
        # 最大容量
        self.capacity = capacity
        # 当前子弹数量
        self.current_list = []

    # 安装子弹
    def save_bullets(self, bullet):
        # 当前子弹数量小于最大容量
        if len(self.current_list) < self.capacity:
            self.current_list.append(bullet)

    def __str__(self):
        return "弹夹当前的子弹数量为：" + str(len(self.current_list)) + "/" + str(self.capacity)

    # 出子弹
    def launch_bullet(self):
        # 判断当前弹夹中中是否还有子弹
        if len(self.current_list) > 0:
            bullet = self.current_list[-1]
            self.current_list.pop()
            return bullet
        else:
            return None

#定义表示子弹的类
class Bullet:
    def __int__(self,damage):
        #伤害力
        self.damage = damage
    #伤害敌人
    def hurt(self,enemy):
        #让敌人掉血
        enemy.lose_blood(self.damage)

#定义表示枪的类
class Gun:
    def __init__(self):
        #默认没有弹夹
        self.clip = None

    def __dir__(self):
        if self.clip:
            return "枪当前有弹夹"
        else:
            return "枪没有弹夹"

    #链接弹夹
    def mounting_clip(self,clip):
        if not self.clip:
            self.clip = clip

    #射击
    def shoot(self,enemy):
        bullet - self.clip.launch_bullet()
        if bullet:
            bullet.hurt(enemy)
        else:
            print("没有子弹了，放了空枪。。。")

# 创建一个战士
soldier = Person("老王")
# 创建一个弹夹
clip = Clip(20)
print(clip)
# 添加5颗子弹
i = 0
while i < 5:
    # 创建一个子弹
    bullet = Bullet(5)
    # 战士安装子弹到弹夹
    soldier.install_bullet(clip, bullet)
    i += 1
#输出当前弹夹中子弹的数量
print(clip)

#创建一个枪
gun = Gun()
print(gun)
#安装弹夹
soldier.install_clip(gun,clip)
print(gun)
#创建一个敌人
enemy = Person("敌人")
print(enemy)
#士兵拿枪
soldier.take_gun(gun)
#士兵开枪
soldier.fire(enemy)
print(clip)
print(enemy)
soldier.fire(enemy)
print(clip)
print(enemy)
