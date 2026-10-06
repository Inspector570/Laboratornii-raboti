
import java.util.Timer;
import java.util.TimerTask;

public class TimerApp {
    public static void main(String[] args) {
        System.out.println("Запуск приложения с таймерами...");

        // Таймер с фиксированным периодом (каждую 1 секунду)
        Timer periodTimer = new Timer();
        periodTimer.scheduleAtFixedRate(new TimerTask() {
            int count = 0;
            @Override
            public void run() {
                count++;
                System.out.println("Прошло секунд: " + count);
                if (count >= 5) {
                    this.cancel();
                    System.out.println("Таймер остановлен.");
                }
            }
        }, 0, 1000);
    }
}
